---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.date: 03/30/2017
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
ms.openlocfilehash: e4466df2ce96760db4790b6545484704c22f0842
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254302"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a>System.ServiceModel.TxCompletionStatusCompletedForError

Заданная транзакция для заданной операции завершена в результате необработанного исключения при выполнении.  
  
## <a name="description"></a>Описание  

 Трассируется, если при попытке завершить текущую транзакцию возникает ошибка. Это происходит до того, как вызвавшему объекту отправляется ответ или ошибка.  
  
## <a name="troubleshooting"></a>Устранение неполадок  

 Проверьте трассируемое сообщение на предмет наличия сообщения об исключении и других элементов, с которыми можно произвести какие-либо действия.  
  
## <a name="see-also"></a>См. также

- [Трассировка](index.md)
- [Использование трассировки для устранения неполадок приложения](using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../index.md)
