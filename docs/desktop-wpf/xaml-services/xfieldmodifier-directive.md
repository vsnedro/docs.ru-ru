---
title: Директива x:FieldModifier
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 4e67a6dac49b8d6a7d316526f99a1519b08fd68b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554479"
---
# <a name="xfieldmodifier-directive"></a>Директива x:FieldModifier
Изменяет поведение компиляции XAML таким образом, чтобы поля для ссылок на именованные объекты определялись с <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> доступом, а не с <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> поведением по умолчанию.

## <a name="xaml-attribute-usage"></a>Использование атрибута XAML

```xaml
<object x:FieldModifier="Public".../>
```

## <a name="xaml-values"></a>Значения XAML

|||
|-|-|
|*Открытый*|Точная строка, которую вы передаете для указания <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , и зависит от используемого языка программирования кода программной части. См. заметки.|

## <a name="dependencies"></a>Зависимости

 Если в рабочей среде XAML используется `x:FieldModifier` где угодно, корневой элемент в этом производстве XAML должен объявить [директиву x:Class](xclass-directive.md).

## <a name="remarks"></a>Примечания

`x:FieldModifier` не относится к объявлению общего уровня доступа класса или его членов. Он важен только для обработки XAML при обработке определенного объекта XAML, который является частью рабочего процесса XAML, и становится объектом, который потенциально доступен в графе объектов приложения. По умолчанию ссылка на поле для такого объекта хранится в закрытом состоянии, что предотвращает возможность непосредственного изменения графа объектов потребителями управления. Вместо этого, потребители элементов управления должны изменить граф объектов с помощью стандартных шаблонов, включенных моделями программирования, например путем получения корня макета, коллекций дочерних элементов, выделенных общих свойств и т. д.

Значение `x:FieldModifier` атрибута зависит от языка программирования, и его назначение может различаться в конкретных платформах. Используемая строка зависит от того, как каждый язык реализует его <xref:System.CodeDom.Compiler.CodeDomProvider> и какие преобразователи типов он возвращает, чтобы определить значения для <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , а также указать, учитывается ли регистр в этом языке.

- Для C# строка, которую необходимо передать для обозначения, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> — `public` .

- Для Microsoft Visual Basic .NET строка, которую необходимо передать для обозначения, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> — это `Public` .

- Для C++/CLI целевые объекты для XAML в настоящее время не существуют; Таким образом, строка для передачи не определена.

Можно также указать <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ( `internal` в C#, `Friend` в Visual Basic), но указание <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> не является необычным, так как `NotPublic` поведение по умолчанию уже используется.

<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> является поведением по умолчанию, поскольку нередко, что код за пределами сборки, в которой скомпилирован XAML, требует доступа к элементу, созданному XAML. Архитектура безопасности WPF вместе с поведением компиляции XAML не приводит к объявлению полей, которые хранят экземпляры элементов как открытые, если только вы явно не установили `x:FieldModifier` для разрешения общего доступа.

`x:FieldModifier` относится только к элементам с [директивой x:Name](xname-directive.md) , так как это имя используется для ссылки на поле после того, как оно является открытым.

По умолчанию разделяемый класс для корневого элемента является открытым; Однако его можно сделать неоткрытым с помощью [директивы КС:классмодифиер](xclassmodifier-directive.md). [Директива КС:классмодифиер](xclassmodifier-directive.md) также влияет на уровень доступа экземпляра класса корневого элемента. Можно разместить `x:Name` и `x:FieldModifier` в корневом элементе, но это только копию открытого поля корневого элемента, при этом уровень доступа класса корневого элемента по-прежнему управляется [директивой КС:классмодифиер](xclassmodifier-directive.md).

## <a name="see-also"></a>См. также

- [Код XAML и пользовательские классы для WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf)
- [Код программной части и XAML в WPF](/dotnet/desktop/wpf/advanced/code-behind-and-xaml-in-wpf)
- [Директива x:Name](xname-directive.md)
- [Создание приложения WPF (WPF)](/dotnet/desktop/wpf/app-development/building-a-wpf-application-wpf)
- [Директива x:ClassModifier](xclassmodifier-directive.md)
