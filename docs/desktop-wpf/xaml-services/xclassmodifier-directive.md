---
title: Директива x:ClassModifier
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 73732a06029cca3a4c6c6d82762d5263c5b8c955
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544821"
---
# <a name="xclassmodifier-directive"></a>Директива x:ClassModifier
Изменяет поведение компиляции XAML, если `x:Class` также предоставляется. В частности, вместо создания частичного `class` уровня, имеющего `Public` уровень доступа (по умолчанию), предоставленный объект `x:Class` создается с `NotPublic` уровнем доступа. Это поведение влияет на уровень доступа для класса в создаваемых сборках.

## <a name="xaml-attribute-usage"></a>Использование атрибута XAML

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a>Значения XAML

|||
|-|-|
|*нотпублик*|Точная строка, которую необходимо передать в <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> параметре, и зависит от используемого языка программирования кода программной части. См. заметки.|

## <a name="dependencies"></a>Зависимости

[x:Class](xclass-directive.md) также должен быть указан в том же элементе, и этот элемент должен быть корневым элементом на странице. Дополнительные сведения см. в [ \[ \] разделе 4.3.1.8 в MS-XAML](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="remarks"></a>Примечания

Значение в параметрах `x:ClassModifier` использования служб XAML .NET зависит от языка программирования. Используемая строка зависит от того, как каждый язык реализует его <xref:System.CodeDom.Compiler.CodeDomProvider> и какие преобразователи типов он возвращает, чтобы определить значения для <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , а также указать, учитывается ли регистр в этом языке.

- Для C# строка, которую необходимо передать для обозначения, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> — `internal` .

- Для Microsoft Visual Basic .NET строка, которую необходимо передать для обозначения, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> — это `Friend` .

- Для C++/CLI не существует целей, поддерживающих компиляцию XAML; Поэтому значение для передачи не указано.

Можно также указать <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ( `public` в C#, `Public` в Visual Basic), однако указание выполняется редко, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> так как <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> уже является поведением по умолчанию.

Другие значения с эквивалентными ограничениями уровня доступа для пользовательского кода, например `private` в C#, не являются значимыми для, `x:ClassModifier` поскольку ссылки на вложенные классы не поддерживаются в XAML, поэтому <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Модификатор имеет тот же результат.

## <a name="security-notes"></a>Примечания по безопасности

Уровень доступа, объявленный в `x:ClassModifier` , по-прежнему подвергается интерпретации определенными платформами и их возможностями. WPF включает возможности для загрузки и создания экземпляров типов `x:ClassModifier` , где имеет значение `internal` , если на этот класс имеется ссылка из ресурса WPF через ссылку на URI типа "Pack". Как следствие этого случая и другие, например, реализованные другими платформами, не полагайтесь исключительно на `x:ClassModifier` блокировку всех возможных попыток создания экземпляров.

## <a name="see-also"></a>См. также

- [Директива x:Class](xclass-directive.md)
- [Код программной части и XAML в WPF](/dotnet/desktop/wpf/advanced/code-behind-and-xaml-in-wpf)
- [Директива x:FieldModifier](xfieldmodifier-directive.md)
- [Безопасность (WPF)](/dotnet/desktop/wpf/security-wpf)
- [Типы, перенесенные из WPF в System.Xaml](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
