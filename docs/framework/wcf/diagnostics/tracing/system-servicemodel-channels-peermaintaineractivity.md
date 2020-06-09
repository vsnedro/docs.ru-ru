---
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.date: 03/30/2017
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
ms.openlocfilehash: ce97eaa2ad5c9dbd5f4d6f81186960c489eb4b85
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596081"
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a>System.ServiceModel.Channels.PeerMaintainerActivity
Модуль PeerMaintainer выполняет определенную операцию (подробности содержатся в теле сообщения трассировки).  
  
## <a name="description"></a>Описание  
 Эта трассировка возникает в ходе различных операций модуля обслуживания PeerMaintainer.  
  
 PeerMaintainer - это внутренний компонент узла PeerNode. Каждую минуту или каждые 32 полученных сообщения он отправляет соседним узлам сообщение LinkUtility со статистическими данными о том, сколько сообщений было принято/отправлено и сколько из них полезны (не дубликаты, не подделаны). Это позволяет определить значение LinkUtility определенного соседнего узла. Приблизительно каждые пять минут модуль обслуживания проверяет состояние соединений с соседними узлами. Если количество соединений с соседними узлами превышает идеальное число, модуль обслуживания урезает наименее полезные соединения. Если соединений недостаточно, модуль обслуживания приобретает новые соединения.  
  
## <a name="see-also"></a>Дополнительно

- [Трассировка](index.md)
- [Использование трассировки для устранения неполадок приложения](using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../index.md)
