---
title: Практическое руководство. Реализация свойства зависимостей
description: Определите свойство зависимостей в Windows Presentation Foundation, создав резервную копию свойства среды CLR с полем DependencyProperty.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: 673f653a9b02627efcccdfe08c4812ca0834217c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165100"
---
# <a name="how-to-implement-a-dependency-property"></a><span data-ttu-id="74283-103">Практическое руководство. Реализация свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="74283-103">How to: Implement a Dependency Property</span></span>
<span data-ttu-id="74283-104">В этом примере показано, как выполнить обратное создание свойства среды CLR с <xref:System.Windows.DependencyProperty> полем, определив таким образом свойство зависимостей.</span><span class="sxs-lookup"><span data-stu-id="74283-104">This example shows how to back a common language runtime (CLR) property with a <xref:System.Windows.DependencyProperty> field, thus defining a dependency property.</span></span> <span data-ttu-id="74283-105">Если вы определяете собственные свойства и хотите, чтобы они поддерживали множество аспектов функциональности [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], включая стили, привязку данных, наследование, анимацию и значения по умолчанию, следует реализовать их как свойства зависимостей.</span><span class="sxs-lookup"><span data-stu-id="74283-105">When you define your own properties and want them to support many aspects of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] functionality, including styles, data binding, inheritance, animation, and default values, you should implement them as a dependency property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74283-106">Пример</span><span class="sxs-lookup"><span data-stu-id="74283-106">Example</span></span>  
 <span data-ttu-id="74283-107">В следующем примере сначала регистрируется свойство зависимости путем вызова <xref:System.Windows.DependencyProperty.Register%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="74283-107">The following example first registers a dependency property by calling the <xref:System.Windows.DependencyProperty.Register%2A> method.</span></span> <span data-ttu-id="74283-108">Имя поля идентификатора, используемого для хранения имени и характеристик свойства зависимостей, должно быть <xref:System.Windows.DependencyProperty.Name%2A> выбрано для свойства зависимостей в рамках <xref:System.Windows.DependencyProperty.Register%2A> вызова, к которому добавляется строка литерала `Property` .</span><span class="sxs-lookup"><span data-stu-id="74283-108">The name of the identifier field that you use to store the name and characteristics of the dependency property must be the <xref:System.Windows.DependencyProperty.Name%2A> you chose for the dependency property as part of the <xref:System.Windows.DependencyProperty.Register%2A> call, appended by the literal string `Property`.</span></span> <span data-ttu-id="74283-109">Например, если зарегистрировать свойство зависимостей с помощью <xref:System.Windows.DependencyProperty.Name%2A> объекта `Location` , то поле идентификатора, определяемое для свойства зависимостей, должно иметь имя `LocationProperty` .</span><span class="sxs-lookup"><span data-stu-id="74283-109">For instance, if you register a dependency property with a <xref:System.Windows.DependencyProperty.Name%2A> of `Location`, then the identifier field that you define for the dependency property must be named `LocationProperty`.</span></span>  
  
 <span data-ttu-id="74283-110">В этом примере имя свойства зависимостей и его метод доступа CLR имеет значение; `State` поле идентификатора имеет значение `StateProperty` ; тип свойства —, <xref:System.Boolean> а тип, регистрирующий свойство зависимостей, — `MyStateControl` .</span><span class="sxs-lookup"><span data-stu-id="74283-110">In this example, the name of the dependency property and its CLR accessor is `State`; the identifier field is `StateProperty`; the type of the property is <xref:System.Boolean>; and the type that registers the dependency property is `MyStateControl`.</span></span>  
  
 <span data-ttu-id="74283-111">Если не следовать этому шаблону именования, конструкторы могут неправильно обработать свойство и определенные аспекты применения стиля в системе свойств могут работать не так, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="74283-111">If you fail to follow this naming pattern, designers might not report your property correctly, and certain aspects of property system style application might not behave as expected.</span></span>  
  
 <span data-ttu-id="74283-112">Для свойства зависимости можно также указать используемые по умолчанию метаданные.</span><span class="sxs-lookup"><span data-stu-id="74283-112">You can also specify default metadata for a dependency property.</span></span> <span data-ttu-id="74283-113">В этом примере в качестве значения по умолчанию для свойства зависимости `State` регистрируется значение `false`.</span><span class="sxs-lookup"><span data-stu-id="74283-113">This example registers the default value of the `State` dependency property to be `false`.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 <span data-ttu-id="74283-114">Дополнительные сведения о том, как и Зачем реализовывать свойство зависимостей, в отличие от простого резервного копирования свойства CLR с закрытым полем, см. в разделе [Общие сведения о свойствах зависимостей](dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="74283-114">For more information about how and why to implement a dependency property, as opposed to just backing a CLR property with a private field, see [Dependency Properties Overview](dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74283-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="74283-115">See also</span></span>

- [<span data-ttu-id="74283-116">Общие сведения о свойствах зависимости</span><span class="sxs-lookup"><span data-stu-id="74283-116">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="74283-117">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="74283-117">How-to Topics</span></span>](properties-how-to-topics.md)
