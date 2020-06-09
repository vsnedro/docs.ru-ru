---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: 8b81cdcaf74aca044260495867b2c4f1de517682
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593754"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a>System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
Не удается переместить или удалить сообщение.  
  
## <a name="description"></a>Описание  
 Эта трассировка показывает, что при попытке переместить, удалить или отклонить сообщение MSMQ произошел сбой.  
  
 Сообщения MSMQ используются Windows Communication Foundation (WCF) (при использовании с NetMsmqBinding или MsmqIntegrationBinding). Эта трассировка связана с выбранным значением свойства в `ReceiveErrorHandling` NetMsmqBinding или MsmqIntegrationBinding.  
  
 Эта трассировка не указывает на общий сбой системы. Однако она показывает, что выбранное средство удаления подозрительного сообщения не подходит для сообщения. Дополнительные сведения о том, когда сообщения становятся подозрительными и как настроить службу для их правильной обработки, см. в разделе [Обработка подозрительных сообщений](../../feature-details/poison-message-handling.md).  
  
## <a name="see-also"></a>Дополнительно

- [Трассировка](index.md)
- [Использование трассировки для устранения неполадок приложения](using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../index.md)
