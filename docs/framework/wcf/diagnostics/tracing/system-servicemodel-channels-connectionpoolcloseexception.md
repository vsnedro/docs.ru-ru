---
description: 'Дополнительные сведения: System. ServiceModel. Channels. Коннектионпулклосиксцептион'
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: a65739cc872f3cd175d76e9113380f9f4185d498
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99644636"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a>System.ServiceModel.Channels.ConnectionPoolCloseException

При закрытии подключений в этом пуле подключений возникло исключение.  
  
## <a name="description"></a>Описание  

 Эта трассировка уровня ошибок указывает на то, что при закрытии пулов соединений, используемых компонентом пулов соединений Windows Communication Foundation (WCF), произошла ошибка. Эта ошибка может быть вызвана тем, что не удалось закрыть подключение (или набор подключений) из пула в течение времени ожидания (CloseTimeout). При выдаче этого исключения все оставшиеся незакрытые подключения из этого пула прерываются. Незакрытые подключения из других пулов оставляются.  
  
## <a name="see-also"></a>См. также

- [Трассировка](index.md)
- [Использование трассировки для устранения неполадок приложения](using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../index.md)
