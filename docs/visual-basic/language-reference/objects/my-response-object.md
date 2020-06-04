---
title: Объект My.Response
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 962108264563c5e0b2894c5c856a5f23a3c1a8b4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372468"
---
# <a name="myresponse-object"></a><span data-ttu-id="5c74c-102">Объект My.Response</span><span class="sxs-lookup"><span data-stu-id="5c74c-102">My.Response Object</span></span>
<span data-ttu-id="5c74c-103">Возвращает <xref:System.Web.HttpResponse> объект, связанный с объектом <xref:System.Web.UI.Page> .</span><span class="sxs-lookup"><span data-stu-id="5c74c-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="5c74c-104">Этот объект позволяет отправлять клиенту данные HTTP-ответа и содержит сведения об этом ответе.</span><span class="sxs-lookup"><span data-stu-id="5c74c-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c74c-105">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5c74c-105">Remarks</span></span>  
 <span data-ttu-id="5c74c-106">`My.Response`Объект содержит текущий объект, <xref:System.Web.HttpResponse> связанный со страницей.</span><span class="sxs-lookup"><span data-stu-id="5c74c-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="5c74c-107">`My.Response`Объект доступен только для приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5c74c-107">The `My.Response` object is only available for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c74c-108">Пример</span><span class="sxs-lookup"><span data-stu-id="5c74c-108">Example</span></span>  
 <span data-ttu-id="5c74c-109">Следующий пример получает коллекцию заголовков из `My.Request` объекта и использует `My.Response` объект для записи на страницу ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5c74c-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5c74c-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5c74c-110">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="5c74c-111">Объект My.Request</span><span class="sxs-lookup"><span data-stu-id="5c74c-111">My.Request Object</span></span>](my-request-object.md)
