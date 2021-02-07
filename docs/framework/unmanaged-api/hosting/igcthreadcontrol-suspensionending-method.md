---
description: 'Дополнительные сведения о методе: IGCThreadControl:: SuspensionEnding'
title: Метод IGCThreadControl::SuspensionEnding
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type:
- apiref
ms.openlocfilehash: 5ff889f45ea3664312060f373907e65c367276f1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709273"
---
# <a name="igcthreadcontrolsuspensionending-method"></a>Метод IGCThreadControl::SuspensionEnding

Уведомляет узел о том, что среда выполнения возобновляет потоки после сборки мусора или другой приостановки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `Generation`  
 окне Поколение, на котором была выполнена сборка мусора.  
  
## <a name="remarks"></a>Remarks  

 Не Перепланируйте потоки во время `SuspensionEnding` обратного вызова.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IGCThreadControl](igcthreadcontrol-interface.md)
