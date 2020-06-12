---
title: -nullable (параметры компилятора C#)
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: a68255dba18a022784cd4aaf0027c371893c577b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2020
ms.locfileid: "84449801"
---
# <a name="-nullable-c-compiler-options"></a>-nullable (параметры компилятора C#)

Параметр **-nullable** позволяет указать требуемый контекст, допускающий значение NULL.

## <a name="syntax"></a>Синтаксис

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a>Аргументы

`+` &#124; `-`  
При указании `+` или просто параметра **-nullable** компилятор включит контекст, допускающий значение NULL. При указании `-`, который действует, если не указан параметр **-nullable**, отключается контекст, допускающий значение NULL.

`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`  
Указывает параметр контекста, допускающий значение NULL. Используется аналогично `+` или `-`, чтобы включать и отключать контекст, но обеспечивает больший уровень детализации для контекста, допускающего значение NULL. Аргумент `enable`, который действует так же, как параметр **-nullable**, включает контекст, допускающий значение NULL. При указании `disable` будет отключен контекст, допускающий значение NULL. При указании аргумента `warnings` **-nullable:warnings** будет включен контекст предупреждения, допускающий значение NULL. При указании аргумента `annotations`, **-nullable:annotations**, будет включен контекст с заметками о допустимости значений NULL.

## <a name="remarks"></a>Примечания

Анализ потока используется для определения допустимости значений NULL в переменных в исполняемом коде. Выводимая допустимость переменной значения NULL не зависит от объявленной в переменной допустимости значения NULL. Вызовы методов анализируются, даже если они условно опущены. Например, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> в режиме выпуска.

Вызов методов, снабженных следующими атрибутами, также повлияет на анализ потока:

- Простые предварительные условия: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> и <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute>
- Простые постусловия: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> и <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute>
- Условные постусловия: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> и <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute>
- <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (например, `DoesNotReturnIf(false)` для <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) и <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- Постусловия элемента: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> и <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])>

### <a name="to-set-this-compiler-option-in-a-project"></a>Установка данного параметра компилятора в проекте

Измените *CSPROJ*-файл, чтобы добавить тег `<Nullable>` в иерархию `Project/PropertyGroup`:

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a>См. также

- [Параметры компилятора C# ](./index.md)
- [Ссылочные типы, допускающие значение NULL](../../nullable-references.md)
