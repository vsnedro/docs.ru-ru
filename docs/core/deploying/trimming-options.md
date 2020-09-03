---
title: Параметры обрезки
description: Узнайте, как управлять обрезкой автономных приложений.
author: sbomer
ms.author: svbomer
ms.date: 08/25/2020
ms.openlocfilehash: 5597d4cdb9e8e96dcec6545e039d43295ca991bd
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142262"
---
# <a name="trimming-options"></a>Параметры обрезки

Следующие свойства и элементы MSBuild влияют на поведение [обрезанных автономных развертываний](trim-self-contained.md). Некоторые параметры упоминают `ILLink`, то есть имя базового инструмента, реализующего обрезку. Дополнительные сведения о программе командной строки `ILLink` см. в разделе [Параметры illink](https://github.com/mono/linker/blob/master/docs/illink-options.md).

## <a name="enable-trimming"></a>Включение обрезки

- `<PublishTrimmed>true</PublishTrimmed>`

   Включите обрезку во время публикации с параметрами по умолчанию, определенными пакетом SDK.

При использовании `Microsoft.NET.Sdk` выполняется обрезка сборок платформы из пакета среды выполнения netcoreapp на уровне сборки. Код приложения и библиотеки, отличные от платформы, не обрезаются. Другие пакеты SDK могут определять разные значения по умолчанию.

## <a name="trimming-granularity"></a>Степень детализации обрезки

Следующие параметры степени детализации управляют тем, насколько агрессивно отбрасываются неиспользуемые IL. Это можно задать как свойство или как метаданные в [отдельной сборке](#Trimmed-assemblies).

- `<TrimMode>copyused</TrimMode>`

   Включите функцию обрезки на уровне сборки, которая будет сохранять всю сборку, если какая-либо ее часть используется (статически понятным образом).

- `<TrimMode>link</TrimMode>`

    Включите функцию обрезки на уровне элементов, которая удаляет неиспользуемые элементы из типов.

Сборки с метаданными `<IsTrimmable>true</IsTrimmable>`, но без явного `TrimMode` будут использовать глобальную `TrimMode`. `TrimMode` по умолчанию для `Microsoft.NET.Sdk` — `copyused`.

## <a name="trimmed-assemblies"></a>Обрезанные сборки

При публикации обрезанного приложения пакет SDK выдает `ItemGroup` с именем `ManagedAssemblyToLink`, который представляет набор файлов для обработки обрезки. `ManagedAssemblyToLink` может иметь метаданные, управляющие поведением обрезки для каждой сборки. Чтобы задать эти метаданные, создайте целевой объект, выполняемый перед встроенным целевым объектом `PrepareForILLink`. В этом примере показано, как включить обрезку `MyAssembly`.

```xml
<Target Name="ConfigureTrimming"
        BeforeTargets="PrepareForILLink">
  <ItemGroup>
    <ManagedAssemblyToLink Condition="'%(Filename)' == 'MyAssembly'">
      <IsTrimmable>true</IsTrimmable>
    </ManagedAssemblyToLink>
  </ItemGroup>
</Target>
```

Не добавляйте и не удаляйте элементы в `ManagedAssemblyToLink`, так как пакет SDK рассчитывает этот набор во время публикации и полагает, что он не изменяется. Поддерживаются следующие метаданные.

- `<IsTrimmable>true</IsTrimmable>`

  Управление тем, обрезана ли данная сборка.

- `<TrimMode>copyused</TrimMode>` или `<TrimMode>link</TrimMode>`

  Управление [степенью детализации](#Trimming-granularity) этой сборки. Имеет приоритет над глобальным `TrimMode`. Установка `TrimMode` для сборки подразумевает `<IsTrimmable>true</IsTrimmable>`.

## <a name="root-assemblies"></a>Корневые сборки

Все сборки, не имеющие `<IsTrimmable>true</IsTrimmable>`, считаются корневыми для анализа. Это означает, что они и все статически понятные зависимости будут сохранены. Дополнительные сборки могут быть корневыми по имени (без расширения `.dll`).

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="MyAssembly" />
</ItemGroup>
```

## <a name="root-descriptors"></a>Корневые дескрипторы

Другой способ указания корней для анализа — использование XML-файла, в котором используется компоновщик [формата дескриптора](https://github.com/mono/linker/blob/master/docs/data-formats.md#descriptor-format). Это позволяет использовать корневые члены вместо целой сборки.

```xml
<ItemGroup>
  <TrimmerRootDescriptor Include="MyRoots.xml" />
</ItemGroup>
```

Например, `MyRoots.xml` может быть корневым для конкретного метода, к которому приложение обращается динамически.

```xml
<linker>
  <assembly fullname="MyAssembly">
    <type fullname="MyAssembly.MyClass">
      <method name="DynamicallyAccessedMethod" />
    </type>
  </assembly>
</linker>
```

## <a name="analysis-warnings"></a>Предупреждения при анализе

Обрезка приведет к удалению IL, который не является статически достижимым. Приложения, использующие отражение или другие шаблоны, которые создают динамические зависимости, могут быть разорваны путем обрезки. Чтобы получать предупреждения об этих шаблонах, выполните следующие действия.

- `<SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>`

    Включите предупреждения при анализе обрезки.

Сюда будут включены предупреждения обо всем приложении, включая собственный код, код библиотеки и код платформы.

## <a name="warning-versions"></a>Версии предупреждений

При анализе обрезки учитывается свойство [`AnalysisLevel`](../project-sdk/msbuild-props.md#AnalysisLevel), которое управляет версией предупреждений при анализе для пакета SDK. Существует еще одно свойство, которое управляет версией предупреждений при анализе обрезки независимо (аналогично `WarningLevel` для компилятора).

- `<ILLinkWarningLevel>5</ILLinkWarningLevel>`

    Настройте отображение только предупреждений заданного или нижнего уровня. Это может быть `9999` для включения всех версий предупреждений.

## <a name="suppressing-warnings"></a>Подавление предупреждений

Отдельные [коды предупреждений](https://github.com/mono/linker/blob/master/docs/error-codes.md#warning-codes) можно подавлять с помощью стандартных свойств MSBuild, которые учитываются цепочкой инструментов, включая `NoWarn`, `WarningsAsErrors`, `WarningsNotAsErrors` и `TreatWarningsAsErrors`. Существует дополнительный параметр, который управляет поведением предупреждения как ошибки ILLink отдельно.

- `<ILLinkTreatWarningsAsErrors>false</ILLinkTreatWarningsAsErrors>`

    Не обрабатывайте предупреждения ILLink как ошибки. Это может быть полезно, чтобы не включать предупреждения при анализе обрезки в ошибки при обработке предупреждений компилятора как ошибок в глобальном масштабе.

## <a name="removing-symbols"></a>Удаление символов

Символы, как правило, усекаются, чтобы соответствовать обрезанным сборкам. Можно также удалить все символы.

- `<TrimmerRemoveSymbols>true</TrimmerRemoveSymbols>`

    Удалите символы из обрезанного приложения, включая внедренные PDB-файлы и отдельные PDB. Это относится как к коду приложения, так и к любым зависимостям, которые входят в состав символов.

Пакет SDK также позволяет отключить поддержку отладчика, используя свойство `DebuggerSupport`. Если поддержка отладчика отключена, то при обрезке символы автоматически удаляются (`TrimmerRemoveSymbols` по умолчанию принимает значение true).
