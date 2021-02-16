---
title: Использование объема протестированного кода для модульного тестирования
description: Узнайте, как использовать возможности объема протестированного кода для модульных тестов .NET.
author: IEvangelist
ms.author: dapine
ms.date: 02/10/2021
ms.openlocfilehash: 492e036593dcdc81f8256b05183c8f0a9e13b414
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100432664"
---
# <a name="use-code-coverage-for-unit-testing"></a>Использование объема протестированного кода для модульного тестирования

Модульные тесты помогают обеспечить функциональность и служат средством для проверки рефакторинга. Объем протестированного кода — это измерение объема кода, выполняемого модульными тестами (строки, ветви или методы). Например, если у вас есть простое приложение с двумя условными ветвями кода (_ветвь a_ и _ветвь b_), модульный тест, проверяющий условную _ветвь a_ сообщит об объеме протестированного кода ветви в 50 %.

В этой статье рассматривается использование объема протестированного кода для модульного тестирования с использованием Coverlet и создания отчетов с помощью ReportGenerator. Несмотря на то что эта статья посвящена C# и xUnit в качестве платформы тестирования, MSTest и NUnit также будут работать. Coverlet — это [проект с открытым исходным кодом на сайте GitHub](https://github.com/coverlet-coverage/coverlet), который предоставляет платформу для платформы объема протестированного кода C#. [Coverlet](https://dotnetfoundation.org/projects/coverlet) является частью .NET Foundation. Coverlet собирает данные тестового запуска покрытия Cobertura, которые используются для создания отчета.

Кроме того, в этой статье подробно описано, как использовать сведения об объеме протестированного кода, собранные из тестового запуска Coverlet, для создания отчета. Создание отчетов возможно с помощью другого проекта [с открытым исходным кодом на сайте GitHub — ReportGenerator](https://github.com/danielpalme/ReportGenerator). ReportGenerator преобразует отчеты о покрытии, созданные Cobertura по многим другим, в удобные для чтения отчеты в различных форматах.

В основе этой статьи лежит [образец проекта исходного кода](/samples/dotnet/samples/unit-testing-code-coverage-cs), доступный в обозревателе примеров.

## <a name="system-under-test"></a>Тестируемая система

Тестируемая система — это код, на котором вы пишете модульные тесты. Это может быть объект, служба или любая другая функция, которая предоставляет возможность тестирования. В этой статье вы создадите библиотеку классов, которая будет тестируемой системой, и два соответствующих проекта модульных тестов.

### <a name="create-a-class-library"></a>Создание библиотеки классов

В командной строке в новом каталоге с именем `UnitTestingCodeCoverage` создайте новую стандартную библиотеку классов .NET с помощью команды [`dotnet new classlib`](../tools/dotnet-new.md#classlib).

```dotnetcli
dotnet new classlib -n Numbers
```

Приведенный ниже фрагмент кода определяет простой класс `PrimeService`, который предоставляет функциональные возможности для проверки того, является ли число простым. Скопируйте приведенный ниже фрагмент кода и замените содержимое файла *Class1.cs*, который был автоматически создан в каталоге *Numbers*. Переименуйте файл *Class1.cs* в *PrimeService.cs*.

```csharp
namespace System.Numbers
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            if (candidate < 2)
            {
                return false;
            }

            for (int divisor = 2; divisor <= Math.Sqrt(candidate); ++divisor)
            {
                if (candidate % divisor == 0)
                {
                    return false;
                }
            }
            return true;
        }
    }
}
```

> [!TIP]
> Стоит упомянуть, что библиотека классов `Numbers` была намеренно добавлена в пространство имен `System`. Это позволяет получить доступ к <xref:System.Math?displayProperty=fullName> без объявления пространства имен `using System;`. Дополнительные сведения см. в разделе [Пространство имен (справка по C#)](../../csharp/language-reference/keywords/namespace.md).

### <a name="create-test-projects"></a>Создание тестовых проектов

Создайте два новых шаблона **тестового проекта xUnit (.NET Core)** из одной командной строки с помощью команды [`dotnet new xunit`](../tools/dotnet-new.md#test):

```dotnetcli
dotnet new xunit -n XUnit.Coverlet.Collector
```

```dotnetcli
dotnet new xunit -n XUnit.Coverlet.MSBuild
```

Оба новых созданных тестовых проекта xUnit должны добавить ссылку на проект библиотеки классов *Numbers*. Это значит, что тестовые проекты имеют доступ к *PrimeService* для тестирования. В командной строке используйте команду [`dotnet add`](../tools/dotnet-add-reference.md):

```dotnetcli
dotnet add XUnit.Coverlet.Collector\XUnit.Coverlet.Collector.csproj reference Numbers\Numbers.csproj
```

```dotnetcli
dotnet add XUnit.Coverlet.MSBuild\XUnit.Coverlet.MSBuild.csproj reference Numbers\Numbers.csproj
```

Проект *MSBuild* назван соответствующим образом, так как он будет зависеть от пакета NuGet [coverlet.msbuild](https://www.nuget.org/packages/coverlet.msbuild). Добавьте эту зависимость пакета, выполнив команду [`dotnet add package`](../tools/dotnet-add-package.md):

```dotnetcli
cd XUnit.Coverlet.MSBuild && dotnet add package coverlet.msbuild && cd ..
```

Предыдущая команда изменила каталоги в области действия на тестовый проект *MSBuild*, а затем добавила пакет NuGet. После этого были изменены каталоги, и выполнен шаг с заходом на один уровень вверх.

Откройте оба файла *UnitTest1.cs* и замените их содержимое следующим фрагментом кода. Переименуйте файлы *UnitTest1.cs* в *PrimeServiceTests.cs*.

```csharp
using System.Numbers;
using Xunit;

namespace XUnit.Coverlet
{
    public class PrimeServiceTests
    {
        readonly PrimeService _primeService;

        public PrimeServiceTests() => _primeService = new PrimeService();

        [
            Theory,
            InlineData(-1), InlineData(0), InlineData(1)
        ]
        public void IsPrime_ValuesLessThan2_ReturnFalse(int value) =>
            Assert.False(_primeService.IsPrime(value), $"{value} should not be prime");

        [
            Theory,
            InlineData(2), InlineData(3), InlineData(5), InlineData(7)
        ]
        public void IsPrime_PrimesLessThan10_ReturnTrue(int value) =>
            Assert.True(_primeService.IsPrime(value), $"{value} should be prime");

        [
            Theory,
            InlineData(4), InlineData(6), InlineData(8), InlineData(9)
        ]
        public void IsPrime_NonPrimesLessThan10_ReturnFalse(int value) =>
            Assert.False(_primeService.IsPrime(value), $"{value} should not be prime");
    }
}
```

### <a name="create-a-solution"></a>Создание решения

В командной строке создайте новое решение для инкапсуляции библиотеки классов и двух тестовых проектов. С помощью команды [`dotnet sln`](../tools/dotnet-sln.md):

```dotnetcli
dotnet new sln -n XUnit.Coverage
```

Это приведет к созданию нового имени файла решения `XUnit.Coverage` в каталоге *UnitTestingCodeCoverage*. Добавьте проекты в корневую папку решения.

## <a name="linux"></a>[Linux](#tab/linux)

```dotnetcli
dotnet sln XUnit.Coverage.sln add **/*.csproj --in-root
```

## <a name="windows"></a>[Windows](#tab/windows)

```dotnetcli
dotnet sln XUnit.Coverage.sln add (ls **/*.csproj) --in-root
```

---

Выполните сборку решения с помощью команды [`dotnet build`](../tools/dotnet-build.md).

```dotnetcli
dotnet build
```

Если сборка выполнена успешно, это означает, что вы создали три проекта, соответствующие проекты и пакеты и обновили исходный код правильно. Отлично!

## <a name="tooling"></a>Инструментарий

Существует два типа средств для проверки объема протестированного кода:

- **Сборщики данных**. Отслеживают выполнение тестов и собирают сведения о тестовых запусках. Они представляют собранные сведения в различных форматах вывода, таких как XML и JSON. Дополнительные сведения см. в статье [Создание своего первого сборщика данных](https://github.com/Microsoft/vstest-docs/blob/master/docs/extensions/datacollector.md).
- **Генераторы отчетов**. Используют данные, собранные из тестовых запусков, для создания отчетов, зачастую в формате HTML.

В этом разделе основное внимание уделяется сборщикам данных. Чтобы использовать Coverlet для проверки объема протестированного кода, существующий проект модульного теста должен иметь соответствующие зависимости пакета или полагаться на [глобальный инструментарий .NET](../tools/global-tools.md), а также на соответствующий пакет NuGet [coverlet.console](https://www.nuget.org/packages/coverlet.console).

## <a name="integrate-with-net-test"></a>Интеграция с тестом .NET

Шаблон тестового проекта xUnit по умолчанию интегрируется с [coverlet.collector](https://www.nuget.org/packages/coverlet.collector).
В командной строке перейдите в каталог проекта *XUnit.Coverlet.Collector* и выполните команду [`dotnet test`](../tools/dotnet-test.md):

```dotnetcli
cd XUnit.Coverlet.Collector && dotnet test --collect:"XPlat Code Coverage"
```

> [!NOTE]
> Аргумент `"XPlat Code Coverage"` — это понятное имя, соответствующее сборщикам данных из Coverlet. Это имя является обязательным (без учета регистра).

В рамках запуска `dotnet test` полученный файл *coverage.cobertura.xml* выводится в каталог *TestResults*. XML-файл содержит результаты. Это межплатформенный вариант, основанный на .NET Core CLI, который отлично подходит для систем сборки, в которых MSBuild недоступен.

Ниже приведен пример файла *coverage.cobertura.xml*.

```xml
<?xml version="1.0" encoding="utf-8"?>
<coverage line-rate="1" branch-rate="1" version="1.9" timestamp="1592248008"
          lines-covered="12" lines-valid="12" branches-covered="6" branches-valid="6">
  <sources>
    <source>C:\</source>
  </sources>
  <packages>
    <package name="Numbers" line-rate="1" branch-rate="1" complexity="6">
      <classes>
        <class name="Numbers.PrimeService" line-rate="1" branch-rate="1" complexity="6"
               filename="Numbers\PrimeService.cs">
          <methods>
            <method name="IsPrime" signature="(System.Int32)" line-rate="1"
                    branch-rate="1" complexity="6">
              <lines>
                <line number="8" hits="11" branch="False" />
                <line number="9" hits="11" branch="True" condition-coverage="100% (2/2)">
                  <conditions>
                    <condition number="7" type="jump" coverage="100%" />
                  </conditions>
                </line>
                <line number="10" hits="3" branch="False" />
                <line number="11" hits="3" branch="False" />
                <line number="14" hits="22" branch="True" condition-coverage="100% (2/2)">
                  <conditions>
                    <condition number="57" type="jump" coverage="100%" />
                  </conditions>
                </line>
                <line number="15" hits="7" branch="False" />
                <line number="16" hits="7" branch="True" condition-coverage="100% (2/2)">
                  <conditions>
                    <condition number="27" type="jump" coverage="100%" />
                  </conditions>
                </line>
                <line number="17" hits="4" branch="False" />
                <line number="18" hits="4" branch="False" />
                <line number="20" hits="3" branch="False" />
                <line number="21" hits="4" branch="False" />
                <line number="23" hits="11" branch="False" />
              </lines>
            </method>
          </methods>
          <lines>
            <line number="8" hits="11" branch="False" />
            <line number="9" hits="11" branch="True" condition-coverage="100% (2/2)">
              <conditions>
                <condition number="7" type="jump" coverage="100%" />
              </conditions>
            </line>
            <line number="10" hits="3" branch="False" />
            <line number="11" hits="3" branch="False" />
            <line number="14" hits="22" branch="True" condition-coverage="100% (2/2)">
              <conditions>
                <condition number="57" type="jump" coverage="100%" />
              </conditions>
            </line>
            <line number="15" hits="7" branch="False" />
            <line number="16" hits="7" branch="True" condition-coverage="100% (2/2)">
              <conditions>
                <condition number="27" type="jump" coverage="100%" />
              </conditions>
            </line>
            <line number="17" hits="4" branch="False" />
            <line number="18" hits="4" branch="False" />
            <line number="20" hits="3" branch="False" />
            <line number="21" hits="4" branch="False" />
            <line number="23" hits="11" branch="False" />
          </lines>
        </class>
      </classes>
    </package>
  </packages>
</coverage>
```

> [!TIP]
> В качестве альтернативы можно использовать пакет MSBuild, если система сборки уже использует MSBuild. В командной строке перейдите в каталог проекта *XUnit.Coverlet.MSBuild* и выполните команду `dotnet test`:
>
> ```dotnetcli
> dotnet test /p:CollectCoverage=true /p:CoverletOutputFormat=cobertura
> ```
>
> Полученный файл *coverage.cobertura.xml* является выходным.
> Вы можете ознакомиться с [руководством по интеграции MSBuild](https://github.com/coverlet-coverage/coverlet/blob/master/Documentation/MSBuildIntegration.md)

## <a name="generate-reports"></a>Создание отчетов

Теперь, когда настроено получение данных из запусков модульного теста, можно создавать отчеты с помощью [ReportGenerator](https://github.com/danielpalme/ReportGenerator). Чтобы установить пакет NuGet [ReportGenerator](https://www.nuget.org/packages/dotnet-reportgenerator-globaltool) в качестве [глобального инструмента .NET](../tools/global-tools.md), используйте команду [`dotnet tool install`](../tools/dotnet-tool-install.md):

```dotnetcli
dotnet tool install -g dotnet-reportgenerator-globaltool
```

Запустите средство и укажите нужные параметры, используя файл выходных данных *coverage.cobertura.xml* из предыдущего тестового запуска.

```console
reportgenerator
"-reports:Path\To\TestProject\TestResults\{guid}\coverage.cobertura.xml"
"-targetdir:coveragereport"
-reporttypes:Html
```

После выполнения этой команды созданный отчет будет представлен в HTML-файле.

:::image type="content" source="media/test-report.png" lightbox="media/test-report.png" alt-text="Отчет, сформированный модульным тестом":::

## <a name="see-also"></a>См. также

- [Объем протестированного кода модульного тестирования Visual Studio](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested)
- [GitHub — репозиторий Coverlet](https://github.com/coverlet-coverage/coverlet)
- [GitHub — репозиторий ReportGenerator](https://github.com/danielpalme/ReportGenerator)
- [Сайт проекта ReportGenerator](https://danielpalme.github.io/ReportGenerator)
- [Команда тестирования .NET Core CLI](../tools/dotnet-test.md)
- [Исходный код примера](/samples/dotnet/samples/unit-testing-code-coverage-cs)

## <a name="next-steps"></a>Следующие шаги

> [!div class="nextstepaction"]
> [Рекомендации по модульному тестированию](unit-testing-best-practices.md)
