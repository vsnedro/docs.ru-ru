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
ms.openlocfilehash: 436204774c2d59b43a77865c666aed702f7681db
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433274"
---
# <a name="xclassmodifier-directive"></a>Директива x:ClassModifier
Изменяет поведение компиляции `x:Class` XAML, когда это также предусмотрено. В частности, вместо `class` создания `Public` частичного уровня доступа (по умолчанию) при условии `x:Class` создается с уровнем `NotPublic` доступа. Такое поведение влияет на уровень доступа для класса в сгенерированных сборках.

## <a name="xaml-attribute-usage"></a>Использование атрибута XAML

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a>Значения XAML

|||
|-|-|
|*Непублично*|Точная строка для <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> уточнения по сравнению варьируется в зависимости от языка программирования, который используется за кодом. См. заметки.|

## <a name="dependencies"></a>Зависимости

[x: Класс](xclass-directive.md) также должен быть предоставлен на том же элементе, и этот элемент должен быть корневым элементом на странице. Для получения дополнительной информации [ \[см.\] ](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))

## <a name="remarks"></a>Примечания

Значение `x:ClassModifier` использования услуг .NET XAML варьируется в зависимости от языка программирования. Строка для использования зависит от того, как каждый язык реализует его <xref:System.CodeDom.Compiler.CodeDomProvider> <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>тип преобразователей он возвращается, чтобы определить значения для и , и является ли этот язык чувствительным к случаю.

- Для C, строка, чтобы <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `internal`пройти к назначению .

- Для Microsoft Visual Basic .NET строка <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `Friend`для передачи в назначенный .

- Для КЗ/CLI не существует целевых показателей, поддерживающих компиляцию XAML; таким образом, значение пройти не уточняется.

Вы также <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> можете`public` указать `Public` (в C , в Visual Basic); однако, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> указание выполняется <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> нечасто, поскольку это уже поведение по умолчанию.

Другие значения с эквивалентными ограничениями уровня `private` доступа к пользовательскому `x:ClassModifier` коду, например, в C, не имеют значения, поскольку вложенные ссылки класса не поддерживаются в XAML, и, следовательно, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> модификатор имеет тот же эффект.

## <a name="security-notes"></a>Примечания по безопасности

Заявленный уровень `x:ClassModifier` доступа по-прежнему регулируется конкретными рамками и их возможностями. WPF включает в себя возможности для `x:ClassModifier` `internal`загрузки и мгновенного типов, где есть, если этот класс ссылается с ресурса WPF через ссылку пакета URI. Как следствие этого случая и потенциально другие, как он реализован другими рамками, не полагаться исключительно на `x:ClassModifier` блокировать все возможные попытки мгновенного.

## <a name="see-also"></a>См. также

- [Директива x:Class](xclass-directive.md)
- [Код программной части и XAML в WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Директива x:FieldModifier](xfieldmodifier-directive.md)
- [Безопасность (WPF)](../../framework/wpf/security-wpf.md)
- [Типы, перенесенные из WPF в System.Xaml](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
