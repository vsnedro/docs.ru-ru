---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: aeeba38eaf674453f4c87cf62f5088c55b5fde2d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290820"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a>System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed

Не удается переместить или удалить сообщение.  
  
## <a name="description"></a>Описание  

 Эта трассировка показывает, что при попытке переместить, удалить или отклонить сообщение MSMQ произошел сбой.  
  
 Сообщения MSMQ используются Windows Communication Foundation (WCF) (при использовании с NetMsmqBinding или MsmqIntegrationBinding). Эта трассировка связана с выбранным значением свойства в `ReceiveErrorHandling` NetMsmqBinding или MsmqIntegrationBinding.  
  
 Эта трассировка не указывает на общий сбой системы. Однако она показывает, что выбранное средство удаления подозрительного сообщения не подходит для сообщения. Дополнительные сведения о том, когда сообщения становятся подозрительными и как настроить службу для их правильной обработки, см. в разделе [Обработка подозрительных сообщений](../../feature-details/poison-message-handling.md).  
  
## <a name="see-also"></a>См. также

- [Трассировка](index.md)
- [Использование трассировки для устранения неполадок приложения](using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../index.md)
