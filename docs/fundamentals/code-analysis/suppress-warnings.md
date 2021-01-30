---
title: Подавлять предупреждения анализа кода
description: Узнайте о различных способах отключения нарушений анализа кода .NET.
ms.date: 01/28/2021
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- code analysis, suppress warnings
- suppress code analysis warnings
ms.openlocfilehash: b08e93089975a59fabfeb0daaf6a2a6454b2c7e8
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99217267"
---
# <a name="how-to-suppress-code-analysis-warnings"></a>Отключение предупреждений анализа кода

В этой статье рассматриваются различные способы отключения предупреждений из анализа кода при сборке приложения .NET.

> [!TIP]
> Если вы используете Visual Studio в качестве среды разработки, меню *лампочки* содержит параметры, создающие код для подавления предупреждений. Дополнительные сведения см. в разделе [подавлять нарушения](/visualstudio/code-quality/use-roslyn-analyzers?#suppress-violations).

## <a name="disable-the-rule"></a>Отключение правила

При отключении правила анализа кода, которое вызывает предупреждение, вы отключаете правило для всего файла или проекта (в зависимости от используемой области [файла конфигурации](configuration-files.md) ). Чтобы отключить правило, установите его серьезность в `none` файле конфигурации.

```ini
[*.{cs,vb}]
dotnet_diagnostic.<rule-ID>.severity = none
```

Дополнительные сведения о серьезности правил см. в разделе [Настройка серьезности правила](~/docs/fundamentals/code-analysis/configuration-options.md#severity-level).

## <a name="use-a-preprocessor-directive"></a>Использование директивы препроцессора

Используйте директиву [#pragma warning (C#)](../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) или [Disable (Visual Basic)](../../visual-basic/language-reference/directives/disable-enable.md) , чтобы отключить предупреждение только для определенной строки кода.

```csharp
    try { ... }
    catch (Exception e)
    {
#pragma warning disable CA2200 // Rethrow to preserve stack details
        throw e;
#pragma warning restore CA2200 // Rethrow to preserve stack details
    }
```

```vb
    Try
        ...
    Catch e As Exception
#Disable Warning CA2200 ' Rethrow to preserve stack details
        Throw e
#Enable Warning CA2200 ' Rethrow to preserve stack details
    End Try
```

## <a name="use-the-suppressmessageattribute"></a>Использование Суппрессмессажеаттрибуте

Можно использовать, <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> чтобы отключить предупреждение либо в исходном файле, либо в глобальном файле подавления для проекта (*GlobalSuppressions.CS* или *глобалсуппрессионс. vb*). Этот атрибут позволяет подавлять предупреждения только в определенных частях проекта или файла.

Два обязательных, позиционированных параметра для <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> атрибута являются *категорией* правила и *идентификатором правила*. Следующий фрагмент кода передает `"Usage"` и `"CA2200:Rethrow to preserve stack details"` для этих параметров.

```csharp
[System.Diagnostics.CodeAnalysis.SuppressMessage("Usage", "CA2200:Rethrow to preserve stack details", Justification = "Not production code.")]
private static void IngorableCharacters()
{
    try
    {
        ...
    }
    catch (Exception e)
    {
        throw e;
    }
}
```

При добавлении атрибута в глобальный файл подавления, например, [область](xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Scope) подавляется до нужного уровня `"member"` . Вы указываете API, где предупреждение следует подавлять с помощью <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Target> Свойства.

```csharp
[assembly: SuppressMessage("Usage", "CA2200:Rethrow to preserve stack details", Justification = "Not production code.", Scope = "member", Target = "~M:MyApp.Program.IngorableCharacters")]
```

Чтобы отключить предупреждения для кода, созданного компилятором, который не соответствует явно предоставленному источнику пользователя, необходимо добавить атрибут подавления в глобальный файл подавления. Например, следующий код подавляет нарушение в конструкторе, созданном компилятором:

```csharp
[module: SuppressMessage("Microsoft.Design", "CA1055:AbstractTypesDoNotHavePublicConstructors", Scope="member", Target="MyTools.Type..ctor()")]
```

## <a name="see-also"></a>См. также раздел

- [Подавлять нарушения (Visual Studio)](/visualstudio/code-quality/use-roslyn-analyzers?#suppress-violations)
