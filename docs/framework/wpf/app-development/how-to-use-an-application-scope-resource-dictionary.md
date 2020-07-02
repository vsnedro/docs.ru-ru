---
title: Практическое руководство. Использование словаря ресурсов области определения приложения
description: Узнайте, как определить и использовать словарь настраиваемых ресурсов области приложения в Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 9d117dea6c554339b4b462b9bf37b80da2dc477f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85613713"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a><span data-ttu-id="b3797-103">Практическое руководство. Использование словаря ресурсов области определения приложения</span><span class="sxs-lookup"><span data-stu-id="b3797-103">How to: Use an Application-Scope Resource Dictionary</span></span>
<span data-ttu-id="b3797-104">В этом примере показано, как определить и использовать пользовательский словарь ресурсов области определения приложения.</span><span class="sxs-lookup"><span data-stu-id="b3797-104">This example shows how to define and use an application-scope custom resource dictionary.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3797-105">Пример</span><span class="sxs-lookup"><span data-stu-id="b3797-105">Example</span></span>  
 <span data-ttu-id="b3797-106"><xref:System.Windows.Application>предоставляет хранилище области приложения для общих ресурсов: <xref:System.Windows.Application.Resources%2A> .</span><span class="sxs-lookup"><span data-stu-id="b3797-106"><xref:System.Windows.Application> exposes an application-scope store for shared resources: <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="b3797-107">По умолчанию <xref:System.Windows.Application.Resources%2A> свойство инициализируется экземпляром <xref:System.Windows.ResourceDictionary> типа.</span><span class="sxs-lookup"><span data-stu-id="b3797-107">By default, the <xref:System.Windows.Application.Resources%2A> property is initialized with an instance of the <xref:System.Windows.ResourceDictionary> type.</span></span> <span data-ttu-id="b3797-108">Этот экземпляр используется при получении и установке свойств области действия приложения с помощью <xref:System.Windows.Application.Resources%2A> .</span><span class="sxs-lookup"><span data-stu-id="b3797-108">You use this instance when you get and set application-scope properties using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="b3797-109">Дополнительные сведения см. [в разделе как получить и задать ресурс области приложения](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b3797-109">For more information, see [How to: Get and Set an Application-Scope Resource](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).</span></span>
  
 <span data-ttu-id="b3797-110">При наличии нескольких ресурсов, которые вы задаете с помощью <xref:System.Windows.Application.Resources%2A> , вместо этого можно использовать настраиваемый словарь ресурсов для хранения этих ресурсов и задать <xref:System.Windows.Application.Resources%2A> вместо него.</span><span class="sxs-lookup"><span data-stu-id="b3797-110">If you have multiple resources that you set using <xref:System.Windows.Application.Resources%2A>, you can instead use a custom resource dictionary to store those resources and set <xref:System.Windows.Application.Resources%2A> with it instead.</span></span> <span data-ttu-id="b3797-111">Ниже показано, как объявить пользовательский словарь ресурсов с помощью XAML.</span><span class="sxs-lookup"><span data-stu-id="b3797-111">The following shows how you declare a custom resource dictionary using XAML.</span></span>
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <span data-ttu-id="b3797-112">Переключение всех словарей ресурсов с помощью <xref:System.Windows.Application.Resources%2A> позволяет поддерживать темы области приложения, в которых каждая тема инкапсулируется одним словарем ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b3797-112">Swapping entire resource dictionaries using <xref:System.Windows.Application.Resources%2A> allows you to support application-scope themes, where each theme is encapsulated by a single resource dictionary.</span></span> <span data-ttu-id="b3797-113">В следующем примере показано, как задать свойство <xref:System.Windows.ResourceDictionary>.</span><span class="sxs-lookup"><span data-stu-id="b3797-113">The following example shows how to set the <xref:System.Windows.ResourceDictionary>.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 <span data-ttu-id="b3797-114">Ниже показано, как можно получить ресурсы области приложения из словаря ресурсов, предоставляемого <xref:System.Windows.Application.Resources%2A> в XAML.</span><span class="sxs-lookup"><span data-stu-id="b3797-114">The following shows how you can get application-scope resources from the resource dictionary exposed by <xref:System.Windows.Application.Resources%2A> in XAML.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 <span data-ttu-id="b3797-115">Ниже показано, как можно получить ресурсы в коде.</span><span class="sxs-lookup"><span data-stu-id="b3797-115">The following shows how you can also get the resources in code.</span></span>  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <span data-ttu-id="b3797-116">При использовании следует учитывать два аспекта <xref:System.Windows.Application.Resources%2A> .</span><span class="sxs-lookup"><span data-stu-id="b3797-116">There are two considerations to make when using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="b3797-117">Во-первых, *ключ* словаря является объектом, поэтому при установке и получении значения свойства необходимо использовать точно такой же экземпляр объекта.</span><span class="sxs-lookup"><span data-stu-id="b3797-117">First, the dictionary *key* is an object, so you must use exactly the same object instance when both setting and getting a property value.</span></span> <span data-ttu-id="b3797-118">(Обратите внимание, что при использовании строки ключ учитывает регистр.) Во-вторых, *значение* словаря является объектом, поэтому необходимо преобразовать значение в нужный тип при получении значения свойства.</span><span class="sxs-lookup"><span data-stu-id="b3797-118">(Note that the key is case-sensitive when using a string.) Second, the dictionary *value* is an object, so you will have to convert the value to the desired type when getting a property value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3797-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b3797-119">See also</span></span>

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [<span data-ttu-id="b3797-120">Ресурсы XAML</span><span class="sxs-lookup"><span data-stu-id="b3797-120">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="b3797-121">Объединенные словари ресурсов</span><span class="sxs-lookup"><span data-stu-id="b3797-121">Merged Resource Dictionaries</span></span>](../advanced/merged-resource-dictionaries.md)
