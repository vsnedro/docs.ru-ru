---
title: Передача URI в среду выполнения Windows
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
ms.openlocfilehash: 7152fb02abf430c0d0e27b82550e4006e3958e93
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288892"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="de05d-102">Передача URI в среду выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="de05d-102">Passing a URI to the Windows Runtime</span></span>
<span data-ttu-id="de05d-103">Методы среды выполнения Windows принимают только абсолютные URI.</span><span class="sxs-lookup"><span data-stu-id="de05d-103">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="de05d-104">Если передать относительный URI в метод среда выполнения Windows, <xref:System.ArgumentException> создается исключение.</span><span class="sxs-lookup"><span data-stu-id="de05d-104">If you pass a relative URI to a Windows Runtime method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="de05d-105">Вот почему: при использовании среда выполнения Windows в .NET Frameworkном коде <xref:Windows.Foundation.Uri?displayProperty=nameWithType> класс отображается как <xref:System.Uri?displayProperty=nameWithType> IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="de05d-105">Here's why: When you use the Windows Runtime in .NET Framework code, the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="de05d-106"><xref:System.Uri?displayProperty=nameWithType>Класс допускает относительные URI, но <xref:Windows.Foundation.Uri?displayProperty=nameWithType> не класс.</span><span class="sxs-lookup"><span data-stu-id="de05d-106">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class does not.</span></span> <span data-ttu-id="de05d-107">Это также справедливо для методов, предоставляемых в среда выполнения Windowsных компонентах.</span><span class="sxs-lookup"><span data-stu-id="de05d-107">This is also true for methods you expose in Windows Runtime Components.</span></span> <span data-ttu-id="de05d-108">Если компонент предоставляет метод, принимающий URI, сигнатура в коде содержит <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="de05d-108">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="de05d-109">Однако для пользователей компонента подпись включает <xref:Windows.Foundation.Uri?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="de05d-109">However, to users of your component, the signature includes <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="de05d-110">URI, переданный вашему компоненту, должен быть абсолютным.</span><span class="sxs-lookup"><span data-stu-id="de05d-110">A URI that is passed to your component must be an absolute URI.</span></span>  
  
<span data-ttu-id="de05d-111">В этом разделе показано, как определить абсолютный URI и как создать его при указании ссылки на ресурс в пакете приложения.</span><span class="sxs-lookup"><span data-stu-id="de05d-111">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="de05d-112">Определение и использование абсолютного URI</span><span class="sxs-lookup"><span data-stu-id="de05d-112">Detecting and using an absolute URI</span></span>  
<span data-ttu-id="de05d-113">Используйте <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> свойство, чтобы убедиться, что URI является абсолютным, прежде чем передать его в среда выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="de05d-113">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the Windows Runtime.</span></span> <span data-ttu-id="de05d-114">Такой подход более эффективен, чем перехват и обработка исключения <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="de05d-114">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="de05d-115">Использование абсолютного URI для ресурса в пакете приложения</span><span class="sxs-lookup"><span data-stu-id="de05d-115">Using an absolute URI for a resource in the app package</span></span>  
<span data-ttu-id="de05d-116">Чтобы указать URI для ресурса в пакете приложения, можно использовать схему `ms-appx` или `ms-appx-web` для создания абсолютного URI.</span><span class="sxs-lookup"><span data-stu-id="de05d-116">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
<span data-ttu-id="de05d-117">В следующем примере показано, как установить <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> свойство для <xref:Windows.UI.Xaml.Controls.WebView> элемента управления и <xref:Windows.UI.Xaml.Controls.Image.Source%2A> свойство для <xref:Windows.UI.Xaml.Controls.Image> элемента управления на ресурсы, содержащиеся в папке с именем Pages, с использованием XAML и кода.</span><span class="sxs-lookup"><span data-stu-id="de05d-117">The following example shows how to set the <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> property for a <xref:Windows.UI.Xaml.Controls.WebView> control and the <xref:Windows.UI.Xaml.Controls.Image.Source%2A> property for an <xref:Windows.UI.Xaml.Controls.Image> control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
<span data-ttu-id="de05d-118">Дополнительные сведения об этих схемах см. в статье [Схемы URI](/windows/uwp/app-resources/uri-schemes) в Центре разработки для Windows.</span><span class="sxs-lookup"><span data-stu-id="de05d-118">For more information about these schemes, see [URI schemes](/windows/uwp/app-resources/uri-schemes) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de05d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="de05d-119">See also</span></span>

- [<span data-ttu-id="de05d-120">Поддержка приложений для Магазина Windows и среды выполнения Windows в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="de05d-120">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](support-for-windows-store-apps-and-windows-runtime.md)
