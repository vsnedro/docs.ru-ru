---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.date: 03/30/2017
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
ms.openlocfilehash: 2bc71d18480fa19be66cbfa1687a7b63eb548309
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601456"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a>System.ServiceModel.TxCompletionStatusCompletedForError
Заданная транзакция для заданной операции завершена в результате необработанного исключения при выполнении.  
  
## <a name="description"></a>Описание  
 Трассируется, если при попытке завершить текущую транзакцию возникает ошибка. Это происходит до того, как вызвавшему объекту отправляется ответ или ошибка.  
  
## <a name="troubleshooting"></a>Диагностика  
 Проверьте трассируемое сообщение на предмет наличия сообщения об исключении и других элементов, с которыми можно произвести какие-либо действия.  
  
## <a name="see-also"></a>Дополнительно

- [Трассировка](index.md)
- [Использование трассировки для устранения неполадок приложения](using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../index.md)
