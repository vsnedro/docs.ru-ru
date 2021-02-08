---
description: 'Дополнительные сведения о: Microsoft. Transactions. Трансактионбридже. РегистерпартиЦипантфаилуре'
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: e930ee66720a9f397999d729e8d680fce9a37e29
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99770629"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a>Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure

Службе протокола WS-AT не удалось зарегистрировать участника для протокола управления.  
  
## <a name="description"></a>Описание  

 Отслеживается, обнаруживает ли MSDTC недопустимый запрос на регистрацию. Это может происходить из-за множественных запросов на регистрацию завершения и внутренних ошибок.  
  
## <a name="troubleshooting"></a>Устранение неполадок  

 Не пытайтесь зарегистрировать завершение несколько раз.  Проверьте строку состояния в сообщении трассировки, чтобы определить, имеются ли элементы, с которыми можно произвести какие-либо действия.  
  
## <a name="see-also"></a>См. также

- [Трассировка](index.md)
- [Использование трассировки для устранения неполадок приложения](using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../index.md)
