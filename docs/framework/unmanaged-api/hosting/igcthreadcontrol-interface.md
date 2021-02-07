---
description: 'Дополнительные сведения о: интерфейс IGCThreadControl'
title: Интерфейс IGCThreadControl
ms.date: 03/30/2017
api_name:
- IGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCThreadControl
helpviewer_keywords:
- IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 3ff04d75-85ac-4df9-886d-dbaa037c0552
topic_type:
- apiref
ms.openlocfilehash: 07c76848668b1525f4ff45ba5de746beefe0e004
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709288"
---
# <a name="igcthreadcontrol-interface"></a>Интерфейс IGCThreadControl

Предоставляет методы для участия в планировании потоков, которые в противном случае были бы заблокированы для сборки мусора.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод SuspensionEnding](igcthreadcontrol-suspensionending-method.md)|Уведомляет узел о том, что среда выполнения возобновляет потоки после сборки мусора или другой приостановки.|  
|[Метод SuspensionStarting](igcthreadcontrol-suspensionstarting-method.md)|Уведомляет узел о том, что среда выполнения начинает приостановку потока для сборки мусора или другой приостановки.|  
|[Метод ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md)|Уведомляет узел о том, что поток, выполняющий вызов, будет заблокирован, возможно, для сборки мусора или другой приостановки.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы размещения](hosting-interfaces.md)
