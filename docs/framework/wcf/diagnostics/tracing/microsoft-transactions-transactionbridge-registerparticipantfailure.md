---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: 2f0198d3c288b4c3833cdac8e5f943ba822c22e9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252027"
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
