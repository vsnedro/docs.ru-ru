---
title: Как использовать ресурсы в локализуемых приложениях
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 8f516a86036656b98add23d38c588b5c19be4d7a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212479"
---
# <a name="how-to-use-resources-in-localizable-apps"></a><span data-ttu-id="d368e-102">Как использовать ресурсы в локализуемых приложениях</span><span class="sxs-lookup"><span data-stu-id="d368e-102">How to: Use resources in localizable apps</span></span>

<span data-ttu-id="d368e-103">Локализация означает адаптацию пользовательского интерфейса для различных языков и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="d368e-103">Localization means to adapt a user interface to different cultures.</span></span> <span data-ttu-id="d368e-104">Для этого необходимо перевести текст, например заголовки, заголовки и элементы списка.</span><span class="sxs-lookup"><span data-stu-id="d368e-104">To do this, text such as titles, captions, and list box items must be translated.</span></span> <span data-ttu-id="d368e-105">Чтобы упростить перевод, преобразуемые элементы собираются в файлы ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d368e-105">To make translation easier, the items to be translated are collected into resource files.</span></span> <span data-ttu-id="d368e-106">Сведения о создании файла ресурсов для локализации см. в статье [Локализация приложения](how-to-localize-an-application.md) .</span><span class="sxs-lookup"><span data-stu-id="d368e-106">See [Localize an app](how-to-localize-an-application.md) for information on how to create a resource file for localization.</span></span> <span data-ttu-id="d368e-107">Чтобы сделать приложение WPF локализованным, разработчики должны собрать все локализуемые ресурсы в сборку ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d368e-107">To make a WPF application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="d368e-108">Сборка ресурсов локализуется на разные языки, и для загрузки кода программной части используется API управления ресурсами.</span><span class="sxs-lookup"><span data-stu-id="d368e-108">The resource assembly is localized into different languages, and the code-behind uses resource management API to load.</span></span>

## <a name="example"></a><span data-ttu-id="d368e-109">Пример</span><span class="sxs-lookup"><span data-stu-id="d368e-109">Example</span></span>

<span data-ttu-id="d368e-110">Одним из файлов, необходимых для приложения WPF, является файл проекта (proj).</span><span class="sxs-lookup"><span data-stu-id="d368e-110">One of the files required for a WPF application is a project file (.proj).</span></span> <span data-ttu-id="d368e-111">Все ресурсы, используемые в приложении, необходимо включить в файл проекта.</span><span class="sxs-lookup"><span data-stu-id="d368e-111">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="d368e-112">Это показано в следующем примере XAML.</span><span class="sxs-lookup"><span data-stu-id="d368e-112">The following XAML example shows this.</span></span>

```xaml
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

<span data-ttu-id="d368e-113">Чтобы использовать ресурс в приложении, создайте экземпляр <xref:System.Resources.ResourceManager> и загрузите ресурс, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="d368e-113">To use a resource in your application, instantiate <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="d368e-114">В следующем коде C# показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="d368e-114">The following C# code demonstrates how to do this.</span></span>

[!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

## <a name="see-also"></a><span data-ttu-id="d368e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d368e-115">See also</span></span>

- [<span data-ttu-id="d368e-116">Локализация приложения</span><span class="sxs-lookup"><span data-stu-id="d368e-116">Localize an app</span></span>](how-to-localize-an-application.md)
