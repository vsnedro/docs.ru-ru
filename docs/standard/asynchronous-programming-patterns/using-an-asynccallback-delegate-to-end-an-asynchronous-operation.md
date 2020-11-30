---
title: Использование делегата AsyncCallback для завершения асинхронной операции
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ending asynchronous operations
- asynchronous programming, ending operations
- AsyncCallback delegate
- stopping asynchronous operations
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
ms.openlocfilehash: 1da6bd95c79b25b5bbf6674cf7e9ef48d19cb708
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677964"
---
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a>Использование делегата AsyncCallback для завершения асинхронной операции

Приложения, которые могут выполнять работу во время ожидания результатов асинхронной операции, не должны блокироваться до завершения этой операции. Используйте один из следующих вариантов, чтобы продолжить выполнение инструкций в период ожидания асинхронной операции.  
  
- Используйте делегат <xref:System.AsyncCallback> для обработки результатов асинхронной операции в отдельном потоке. Именно этот подход демонстрируется в этой статье.  
  
- Чтобы определить, завершена ли операция, используется свойство <xref:System.IAsyncResult.IsCompleted%2A> объекта <xref:System.IAsyncResult>, возвращаемого методом **Begin**_имя_операции_ асинхронной операции. Пример, демонстрирующий этот подход, см. в разделе [Запрос состояния асинхронной операции](polling-for-the-status-of-an-asynchronous-operation.md).  
  
## <a name="example"></a>Пример  

 В следующем примере кода асинхронные методы класса <xref:System.Net.Dns> используются для получения из службы доменных имен (DNS) сведений об указанных пользователем компьютерах. Этот пример создает делегат <xref:System.AsyncCallback>, который ссылается на метод `ProcessDnsInformation`. Этот метод вызывается один раз для каждого асинхронного запроса сведений DNS.  
  
 Обратите внимание, что в параметре <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object> передается узел, указанный пользователем. Пример, демонстрирующий определения и использования более сложного объекта состояния, представлен в статье [Использование делегата AsyncCallback и объекта состояния](using-an-asynccallback-delegate-and-state-object.md).  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a>См. также раздел

- [Асинхронная модель на основе событий (EAP)](event-based-asynchronous-pattern-eap.md)
- [Обзор асинхронной модели, основанной на событиях](event-based-asynchronous-pattern-overview.md)
- [Вызов асинхронных методов с помощью IAsyncResult](calling-asynchronous-methods-using-iasyncresult.md)
- [Использование делегата AsyncCallback и объекта состояния](using-an-asynccallback-delegate-and-state-object.md)
