---
description: 'Дополнительные сведения: System. ServiceModel. Channels. Хттпчаннелмессажерецеивефаилед'
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: 41c31305fabc369faedec460fc3a042426d45e37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769875"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a>System.ServiceModel.Channels.HttpChannelMessageReceiveFailed

Сбой получения сообщения по каналу HTTP.  
  
## <a name="description"></a>Описание  

 Данная трассировка может выдаваться в качестве предупреждения или ошибки. В обоих случаях трассировка выдается, если при входящем HTTP-запросе не найден совместимый прослушиватель и HTTP-запрос получил отказ. Это может произойти по той причине, что HTTP-команда запроса не была распознана прослушивателем HTTP, либо потому что прослушиватель ожидал передачи данных по адресу, на который был направлен запрос. Данная трассировка выдается как предупреждение при независимом размещении и как ошибка при размещении службы в IIS.  
  
## <a name="see-also"></a>См. также

- [Трассировка](index.md)
- [Использование трассировки для устранения неполадок приложения](using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../index.md)
