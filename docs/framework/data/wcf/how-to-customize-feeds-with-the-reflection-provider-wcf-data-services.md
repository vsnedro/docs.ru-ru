---
description: Дополнительные сведения см. в статье Настройка веб-каналов с помощью поставщика отражения (службы данных WCF).
title: Практическое руководство. Настройка каналов с поставщиком отражения (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: 00c23dcf-9bb8-459a-a012-6c4d9bcad7e9
ms.openlocfilehash: 91ac9cd3a5e882714335ce1d4ef29510d4640534
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765637"
---
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a>Практическое руководство. Настройка каналов с поставщиком отражения (службы данных WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Службы данных WCF позволяет настроить сериализацию Atom в ответе службы данных, чтобы свойства сущности могли быть сопоставлены с неиспользуемыми элементами, определенными в протоколе AtomPub. Этот раздел показывает, как настроить атрибуты сопоставления типов сущностей в модели данных, определенной с помощью поставщика отражения. Дополнительные сведения см. в разделе [Настройка веб-канала](feed-customization-wcf-data-services.md).  
  
 Модель данных для этого примера определяется в разделе [как создать службу данных с помощью поставщика отражения.](create-a-data-service-using-rp-wcf-data-services.md)  
  
## <a name="example"></a>Пример  

 В следующем примере оба свойства типа `Order` отображаются на существующие элементы Atom. Свойство `Product` типа `Item` отображается на специализированный атрибут канала в отдельном пространстве имен.  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a>Пример  

 Предыдущий пример возвращает следующий результат для URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a>См. также

- [Поставщик отражения](reflection-provider-wcf-data-services.md)
