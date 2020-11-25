---
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
ms.openlocfilehash: 02facbb0ff1c0f8978d4f4f720ab370f70f07fe2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721690"
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
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы размещения](hosting-interfaces.md)
