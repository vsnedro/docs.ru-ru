---
title: Объект My.Request
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: d0459506994fb69ebfaa4186ba137044b6fe9464
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870081"
---
# <a name="myrequest-object"></a>Объект My.Request

Возвращает объект <xref:System.Web.HttpRequest> для запрашиваемой страницы.  
  
## <a name="remarks"></a>Remarks  

 Объект `My.Request` содержит сведения о текущем HTTP-запросе.  
  
 Объект `My.Request` доступен только для приложений ASP.NET.  
  
## <a name="example"></a>Пример  

 Следующий пример получает коллекцию заголовков из `My.Request` объекта и использует `My.Response` объект для записи на страницу ASP.NET.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Web.HttpRequest>
- [Объект My.Response](my-response-object.md)
