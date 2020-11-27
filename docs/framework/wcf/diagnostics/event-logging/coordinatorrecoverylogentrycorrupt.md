---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: c3174e70d42385923674a3db5f696a0f64eda29f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295368"
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
