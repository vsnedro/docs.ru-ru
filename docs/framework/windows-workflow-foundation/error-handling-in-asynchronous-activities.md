---
title: Ошибка при обработке асинхронных действий
ms.date: 03/30/2017
ms.assetid: e8f8ce2b-50c9-4e44-b187-030e0cf30a5d
ms.openlocfilehash: 2c214ce1d0f435cda79deb6976ca9196a5d7aee1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280264"
---
# <a name="error-handling-in-asynchronous-activities"></a>Ошибка при обработке асинхронных действий

Обеспечение обработки ошибок в <xref:System.Activities.AsyncCodeActivity> включает маршрутизацию ошибки в системе обратного вызова действия. В этом разделе описывается, как возвратить ошибку, вызванную в асинхронной операции, обратно в узел, используя образец действия SendMail.  
  
## <a name="returning-an-error-thrown-in-an-asynchronous-activity-back-to-the-host"></a>Возвращение ошибки, вызванной в асинхронном действии, обратно на узел  

 Маршрутизация ошибки в асинхронной операции обратно на узел в образце действия SendMail включает следующие шаги.  
  
- Добавьте свойство Exception к классу `SendMailAsyncResult`.  
  
- Скопируйте вызванную ошибку в это свойство в обработчике событий `SendCompleted`.  
  
- Создайте исключение в обработчике событий `EndExecute`.  
  
 Ниже приведен конечный код.  
  
```csharp  
class SendMailAsyncResult : IAsyncResult  
        {  
            …  
            public Exception Error { get; set; }
            …  
            void SendCompleted(object sender, AsyncCompletedEventArgs e)  
            {  
                Error = e.Error;  
                this.asyncWaitHandle.Set();  
                callback(this);  
            }  
         }  
  
    public sealed class SendMail: AsyncCodeActivity  
    {  
         …  
        protected override void EndExecute(AsyncCodeActivityContext context, IAsyncResult result)  
        {  
            SendMailAsyncResult sendMailResult = result as SendMailAsyncResult;  
            if (sendMailResult != null && sendMailResult.Error != null)  
                throw sendMailResult.Error;
        }  
    }  
```
