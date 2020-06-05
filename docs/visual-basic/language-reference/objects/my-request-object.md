---
title: Объект My.Request
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 38f510e2a3958761b902f37760069aa8d595ea8e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372431"
---
# <a name="myrequest-object"></a>Объект My.Request
Возвращает объект <xref:System.Web.HttpRequest> для запрашиваемой страницы.  
  
## <a name="remarks"></a>Комментарии  
 Объект `My.Request` содержит сведения о текущем HTTP-запросе.  
  
 Объект `My.Request` доступен только для приложений ASP.NET.  
  
## <a name="example"></a>Пример  
 Следующий пример получает коллекцию заголовков из `My.Request` объекта и использует `My.Response` объект для записи на страницу ASP.NET.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Web.HttpRequest>
- [Объект My.Response](my-response-object.md)
