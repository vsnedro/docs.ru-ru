---
title: расширение разметки x:Reference
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: f06e259893111a436e5afe2df754c3edee326d54
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432656"
---
# <a name="xreference-markup-extension"></a><span data-ttu-id="3b56b-102">расширение разметки x:Reference</span><span class="sxs-lookup"><span data-stu-id="3b56b-102">x:Reference Markup Extension</span></span>

<span data-ttu-id="3b56b-103">Ссылки на экземпляр, объявленный в другом месте в разметке XAML.</span><span class="sxs-lookup"><span data-stu-id="3b56b-103">References an instance that is declared elsewhere in XAML markup.</span></span> <span data-ttu-id="3b56b-104">Ссылка относится к `x:Name`элементу .</span><span class="sxs-lookup"><span data-stu-id="3b56b-104">The reference refers to an element's `x:Name`.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="3b56b-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="3b56b-105">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Reference instancexName}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="3b56b-106">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="3b56b-106">XAML Object Element Usage</span></span>

```xaml
<object>
  <object.property>
    <x:Reference Name="instancexName"/>
  </object.property>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="3b56b-107">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="3b56b-107">XAML Values</span></span>

|||
|-|-|
|`instancexName`|<span data-ttu-id="3b56b-108">Значение `x:Name` (или значение <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>идентифицированного свойства) указанного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="3b56b-108">The `x:Name` value (or value of the <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified property) of the referenced instance.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3b56b-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="3b56b-109">Remarks</span></span>

<span data-ttu-id="3b56b-110">`x:Reference`обеспечивает поддержку на уровне языков XAML для концепции ссылки на элементы, которая в противном случае была реализована в конкретных рамках, таких как WPF.</span><span class="sxs-lookup"><span data-stu-id="3b56b-110">`x:Reference` provides XAML language-level support for an element reference concept that was otherwise implemented in specific frameworks such as WPF.</span></span>

## <a name="xreference-and-wpf"></a><span data-ttu-id="3b56b-111">x:Справка и WPF</span><span class="sxs-lookup"><span data-stu-id="3b56b-111">x:Reference and WPF</span></span>

<span data-ttu-id="3b56b-112">В WPF и XAML 2006 ссылки на элементы <xref:System.Windows.Data.Binding.ElementName%2A> рассматриваются с помощью функции связывания на уровне рамочной системы.</span><span class="sxs-lookup"><span data-stu-id="3b56b-112">In WPF and XAML 2006, element references are addressed by the framework-level feature of <xref:System.Windows.Data.Binding.ElementName%2A> binding.</span></span> <span data-ttu-id="3b56b-113">Для большинства приложений и <xref:System.Windows.Data.Binding.ElementName%2A> сценариев WPF по-прежнему следует использовать привязку.</span><span class="sxs-lookup"><span data-stu-id="3b56b-113">For most WPF applications and scenarios, <xref:System.Windows.Data.Binding.ElementName%2A> binding should still be used.</span></span> <span data-ttu-id="3b56b-114">Исключенияизмвателями в это общее руководство могут быть случаи, когда существует контекст данных или другие соображения, которые делают нецелесообразными связывание данных и когда компиляция разметки не участвует.</span><span class="sxs-lookup"><span data-stu-id="3b56b-114">Exceptions to this general guidance might include cases where there are data context or other scoping considerations that make data binding impractical and where markup compilation is not involved.</span></span>

<span data-ttu-id="3b56b-115">`x:Reference`— конструкция, определяемая в XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="3b56b-115">`x:Reference` is a construct defined in XAML 2009.</span></span> <span data-ttu-id="3b56b-116">В WPF можно использовать возможности XAML 2009, но только для кода XAML, не скомпилированного с разметкой WPF.</span><span class="sxs-lookup"><span data-stu-id="3b56b-116">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="3b56b-117">Скомпилированный XAML с разметкой и форма BAML кода XAML пока не поддерживают ключевые слова языка и компоненты XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="3b56b-117">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>
