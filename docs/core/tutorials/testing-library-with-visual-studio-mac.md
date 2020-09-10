---
title: Тестирование библиотеки классов .NET Standard с помощью .NET Core и Visual Studio для Mac
description: Создайте проект модульного теста для библиотеки классов .NET Core. Проверьте правильность работы библиотеки классов .NET Core с помощью модульных тестов.
ms.date: 06/08/2020
ms.openlocfilehash: d3c8a5e01d16047949e977f3af6a429970d996d0
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359224"
---
# <a name="test-a-net-standard-class-library-with-net-core-using-visual-studio"></a>Тестирование библиотеки классов .NET Standard с помощью .NET Core и Visual Studio

В этом руководстве показано, как автоматизировать модульное тестирование путем добавления тестового проекта в решение.

## <a name="prerequisites"></a>Предварительные требования

- В этом учебнике используется решение, созданное при работе со статьей [Создание библиотеки .NET Standard в Visual Studio для Mac](library-with-visual-studio-mac.md).

## <a name="create-a-unit-test-project"></a>Создание проекта модульного теста

Модульные тесты обеспечивают автоматическое тестирование программного обеспечения во время разработки и публикации. [MSTest](https://github.com/Microsoft/testfx-docs) — это одна из трех доступных для выбора платформ тестирования. Другими являются [xUnit](https://xunit.net/) и [nUnit](https://nunit.org/).

1. Запустите Visual Studio для Mac.

1. Откройте решение `ClassLibraryProjects`, созданное при работе со статьей [Создание библиотеки .NET Standard в Visual Studio для Mac](library-with-visual-studio-mac.md).

1. На панели **Решение** щелкните решение `ClassLibraryProjects` при нажатой клавише <kbd>CTRL</kbd> и выберите пункт **Добавить** > **Новый проект**.

1. В узле **Web and Console** (Интернет и консоль) диалогового окна **Создание проекта** выберите **Тесты**. Выберите **Проект MSTest** и нажмите кнопку **Далее**.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-project.png" alt-text="Создание тестового проекта в диалоговом окне Создание проекта Visual Studio для Mac":::

1. Выберите **.NET Core 3.1**. Назовите новый проект StringLibraryTest и выберите **Создать**.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-new-project-name.png" alt-text="Диалоговое окно Создание проекта Visual Studio для Mac с именем проекта":::

   Visual Studio создает файл класса, используя следующий код:

   ```csharp
   using Microsoft.VisualStudio.TestTools.UnitTesting;

   namespace StringLibraryTest
   {
       [TestClass]
       public class UnitTest1
       {
           [TestMethod]
           public void TestMethod1()
           {
           }
       }
   }
   ```

   Исходный код, созданный шаблоном модульного теста, выполняет следующие действия.

   - Он импортирует пространство имен <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, которое содержит типы, используемые для модульного тестирования.
   - Он применяет атрибут <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> к классу `UnitTest1`.
   - Он применяет атрибут <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> для `TestMethod1`.

   При запуске модульного теста автоматически выполняются все методы теста, помеченные атрибутом [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute), в тестовом классе, помеченном атрибутом [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute).

## <a name="add-a-project-reference"></a>Добавление ссылки на проект

Чтобы тестовый проект работал с классом `StringLibrary`, добавьте ссылку на проект `StringLibrary`.

1. На панели **Решение** щелкните элемент **Зависимости** при нажатой клавише <kbd>CTRL</kbd> в области **StringLibraryTest**. Выберите пункт **Добавить ссылку** в контекстном меню.

1. В диалоговом окне **Ссылки** выберите проект **StringLibrary**. Нажмите кнопку **ОК**.

      :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-edit-references.png" alt-text="Диалоговое окно Изменение ссылок Visual Studio для Mac":::

## <a name="add-and-run-unit-test-methods"></a>Добавление и выполнение методов модульного теста

При запуске модульного теста Visual Studio выполняет каждый метод, помеченный атрибутом <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute>, в классе, помеченном атрибутом <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>. Метод теста завершается, когда происходит первый сбой или когда все тесты, содержащиеся в методе, будут успешно выполнены.

В самых распространенных тестах вызываются члены класса <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>. Многие методы утверждения (Assert) принимают по крайней мере два параметра, из которых один представляет ожидаемый результат теста, а второй — фактический результат теста. Наиболее популярные из этих методов класса `Assert` перечислены в следующей таблице:

| Методы утверждения     | Функция |
| ------------------ | -------- |
| `Assert.AreEqual`  | Проверяет равенство двух значений или объектов. Утверждение не выполняется, если значения или объекты не равны. |
| `Assert.AreSame`   | Проверяет, что две объектные переменные ссылаются на один и тот же объект. Утверждение не выполняется, если переменные ссылаются на разные объекты. |
| `Assert.IsFalse`   | Проверяет, что условие имеет значение `false`. Утверждение не выполняется, если условие имеет значение `true`. |
| `Assert.IsNotNull` | Проверяет, что объект не имеет значение `null`. Утверждение не выполняется, если объект является `null`. |

Вы можете также использовать метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> в методе теста, чтобы указать тип исключения, которое он должен создавать. Такой тест считается не выполненным, если заявленное исключение не было создано.

Для тестирования метода `StringLibrary.StartsWithUpper` необходимо предоставить несколько строк, которые начинаются с символов верхнего регистра. Предполагается, что в этих случаях метод возвратит `true`, поэтому можно вызвать метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType>. Представьте также несколько строк, которые не начинаются с символов верхнего регистра. Предполагается, что в этих случаях метод возвратит `false`, поэтому можно вызвать метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType>.

Так как ваш метод библиотеки обрабатывает строки, нам нужно проверить правильность обработки [пустых строк (`String.Empty`)](xref:System.String.Empty) (так называется допустимая строка, которая не содержит символов и для которой свойство <xref:System.String.Length> имеет значение 0) и строки `null`, которая не была инициализирована. Метод `StartsWithUpper` можно вызвать напрямую как статический метод и передать ему один аргумент типа <xref:System.String>. Или метод `StartsWithUpper` можно вызвать как метод расширения для переменной `string`, которой назначено значение `null`.

Вы определите три метода, каждый из которых вызывает метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> для каждого элемента в массиве строк. Вы вызовете перегруженную версию метода, которая позволяет указать сообщение об ошибке, отображаемое в случае сбоя теста. В этом сообщении определяется строка, вызвавшая сбой.

Создание методов теста:

1. Откройте файл *UnitTest1.cs* и замените его содержимое на следующий код:

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   Тест на символы верхнего регистра в методе `TestStartsWithUpper` включает заглавную греческую букву "альфа" (U+0391) и заглавную кириллическую букву "М" (U+041C). Тест на символы нижнего регистра в методе `TestDoesNotStartWithUpper` включает строчную греческую букву "альфа" (U+03B1) и строчную кириллическую букву "г" (U+0433).

1. В строке меню выберите **Файл** > **Сохранить как**. В диалоговом окне проверьте, что поле **Кодировка** имеет значение **Юникод (UTF-8)** .

   :::image type="content" source="media/testing-library-with-visual-studio-mac/save-file-as-dialog.png" alt-text="Диалоговое окно Сохранить файл как в Visual Studio":::

1. Когда вам предложат заменить существующий файл, выберите **Заменить**.

   Если вы не сохраните исходный код в кодировке UTF8, Visual Studio может сохранить его как файл ASCII. В этом случае среде выполнения не удастся правильно раскодировать символы UTF8 за пределами стандартного диапазона ASCII, и результаты теста будут неправильными.

1. Откройте панель **Модульные тесты** в правой части экрана. В меню выберите **Просмотр** > **Тесты**.

1. Щелкните значок **Закрепить**, чтобы панель не закрывалась.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-dock-icon.png" alt-text="Значок закрепления на панели Модульные тесты в Visual Studio для Mac":::

1. Нажмите кнопку **Запустить все**.

   Все тесты пройдены.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-pass.png" alt-text="Ожидаемое прохождение теста в Visual Studio для Mac":::

## <a name="handle-test-failures"></a>Обработка сбоев теста

Выполняя разработку на основе тестирования (TDD), вы сначала пишете тесты, и они завершаются сбоем при первом запуске. Затем вы добавляете код в приложение, и тест успешно выполняется. В рамках этого учебника вы создали тест после написания кода приложения для его проверки, поэтому тест был пройден. Чтобы проверить, завершается ли тест ошибкой, как и ожидается, добавьте недопустимое значение во входные данные теста.

1. Измените массив `words` в методе `TestDoesNotStartWithUpper`, включив в него строку "Error". Сохранять файл не требуется, поскольку при сборке решения для выполнения тестов Visual Studio автоматически сохраняет открытые файлы.

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. Повторно запустите тесты.

   В этот раз в окне **Обозреватель тестов** будет указано, что два теста выполнены успешно, а третий завершился ошибкой.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/failed-test-window.png" alt-text="Окно Обозреватель тестов с тестами, которые завершились ошибкой":::

1. Щелкните непройденный тест `TestDoesNotStartWithUpper` при нажатой клавише <kbd>CTRL</kbd> и в контекстном меню выберите **Показать панель результатов**.

   На панели **Результаты** появится сообщение, созданное методом утверждения: "Assert.IsFalse failed. Expected for 'Error': false; actual: True". Из-за этого сбоя строки в массиве, расположенные после слова "Error", не проверялись.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-failure.png" alt-text="Окно Обозреватель тестов с сообщением о том, что утверждение IsFalse ошибочно":::

1. Удалите строку "Error", которую вы добавили на шаге 1. Еще раз запустите тест. Теперь тесты будут пройдены.

## <a name="test-the-release-version-of-the-library"></a>Тестирование версии выпуска для библиотеки

Теперь, когда все тесты пройдены при выполнении сборки в режиме отладки, следует запустить все тесты еще раз, теперь уже для сборки библиотеки в режиме выпуска. Некоторые факторы, например оптимизации компилятора, иногда могут вызывать разное поведение сборки в режимах отладки и выпуска.

Протестируйте сборку выпуска следующим образом.

1. В панели инструментов Visual Studio измените конфигурацию сборки с режима **Отладка** на **Выпуск**.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-toolbar-release.png" alt-text="Панель инструментов Visual Studio с выделенной сборкой выпуска":::

1. На панели **Решение** щелкните проект **StringLibrary** при нажатой клавише <kbd>CTRL</kbd> и выберите в контекстном меню пункт **Сборка**, чтобы выполнить повторную компиляцию библиотеки.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/build-library-context-menu.png" alt-text="Контекстное меню проекта StringLibrary с командой сборки":::

1. Повторно запустите модульные тесты.

   Все тесты будут пройдены.

## <a name="debug-tests"></a>Отладка тестов

Вы можете использовать тот же процесс, который приведен в статье [Учебник. Отладка консольного приложения .NET Core с помощью Visual Studio для Mac](debugging-with-visual-studio-mac.md), чтобы выполнить отладку кода с помощью проекта модульного теста. Вместо запуска проекта приложения ShowCase щелкните проект **StringLibraryTests** при нажатой клавише <kbd>CTRL</kbd> и выберите **Начать отладку проекта** в контекстном меню. Visual Studio запускает тестовый проект с присоединенным отладчиком. Выполнение будет прервано в любой точке останова, добавленной в тестовый проект или базовый код библиотеки.

## <a name="additional-resources"></a>Дополнительные ресурсы

* [Модульное тестирование в .NET Core и .NET Standard](../testing/index.md)

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы выполнили модульное тестирование библиотеки классов. Чтобы сделать библиотеку доступной другим пользователям, опубликуйте ее в [NuGet](https://nuget.org) в качестве пакета. Чтобы узнать, как это делать, следуйте указаниям в руководстве по NuGet:

> [!div class="nextstepaction"]
> [Создание и публикация пакета (dotnet CLI)](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

Если библиотека опубликована как пакет NuGet, ее могут устанавливать и использовать другие пользователи. Чтобы узнать, как это делать, следуйте указаниям в руководстве по NuGet:

> [!div class="nextstepaction"]
> [Установка и использование пакета Visual Studio для Mac](/nuget/quickstart/install-and-use-a-package-in-visual-studio-mac)

Библиотеку не нужно распространять как пакет. Ее можно объединить с консольным приложением, где она используется. Чтобы узнать, как опубликовать консольное приложение, ознакомьтесь с предыдущим руководством в этой серии:

> [!div class="nextstepaction"]
> [Публикация консольного приложения .NET Core с помощью Visual Studio для Mac](publishing-with-visual-studio-mac.md)
