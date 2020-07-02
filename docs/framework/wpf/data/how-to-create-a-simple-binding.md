---
title: Практическое руководство. Создать простой привязки
description: Создайте простую привязку для приложений с помощью этого примера в Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 63dc44b442bb4658382bf12faf57b51c8e0698bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618705"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="04e70-103">Практическое руководство. Создать простой привязки</span><span class="sxs-lookup"><span data-stu-id="04e70-103">How to: Create a Simple Binding</span></span>
<span data-ttu-id="04e70-104">В этом примере показано, как создать простой <xref:System.Windows.Data.Binding> .</span><span class="sxs-lookup"><span data-stu-id="04e70-104">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04e70-105">Пример</span><span class="sxs-lookup"><span data-stu-id="04e70-105">Example</span></span>  
 <span data-ttu-id="04e70-106">В этом примере у вас есть `Person` объект со строковым свойством с именем `PersonName` .</span><span class="sxs-lookup"><span data-stu-id="04e70-106">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="04e70-107">`Person`Объект определяется в пространстве имен с именем `SDKSample` .</span><span class="sxs-lookup"><span data-stu-id="04e70-107">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="04e70-108">Выделенная строка, содержащая `<src>` элемент в следующем примере, создает экземпляр `Person` объекта со `PersonName` значением свойства `Joe` .</span><span class="sxs-lookup"><span data-stu-id="04e70-108">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="04e70-109">Это делается в `Resources` разделе и назначено `x:Key` .</span><span class="sxs-lookup"><span data-stu-id="04e70-109">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="04e70-110">Выделенная строка, содержащая `<TextBlock>` элемент, привязывает <xref:System.Windows.Controls.TextBlock> элемент управления к `PersonName` свойству.</span><span class="sxs-lookup"><span data-stu-id="04e70-110">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="04e70-111">В результате <xref:System.Windows.Controls.TextBlock> отображается со значением Joe.</span><span class="sxs-lookup"><span data-stu-id="04e70-111">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04e70-112">См. также</span><span class="sxs-lookup"><span data-stu-id="04e70-112">See also</span></span>

- [<span data-ttu-id="04e70-113">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="04e70-113">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="04e70-114">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="04e70-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
