---
description: 'Дополнительные сведения о: Курдинаторрековериложентрикоррупт'
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: 3a848c634a226b34023a24898f9827162b4dafc7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771344"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a>CoordinatorRecoveryLogEntryCorrupt

Идентификатор: 139  
  
 Важность: ошибка  
  
 Категория: TransactionBridge  
  
## <a name="description"></a>Описание  

 Это событие показывает, что запись в журнале восстановления координатора была повреждена и ее не удалось десериализовать. Эта ошибка может привести к потере данных. В событии указаны идентификатор транзакции, данные о восстановлении (в кодировке Base64), исключение, имя и ИД процесса.  
  
## <a name="see-also"></a>См. также

- [Ведение журналов событий](index.md)
- [Общие справочные сведения о событиях](events-general-reference.md)
