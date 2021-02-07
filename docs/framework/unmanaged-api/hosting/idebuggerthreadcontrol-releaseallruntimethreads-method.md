---
description: 'Дополнительные сведения о методе: Идебугжерсреадконтрол:: Релеасеаллрунтимесреадс'
title: Метод IDebuggerThreadControl::ReleaseAllRuntimeThreads
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ReleaseAllRuntimeThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ReleaseAllRuntimeThreads
helpviewer_keywords:
- ReleaseAllRuntimeThreads method [.NET Framework hosting]
- IDebuggerThreadControl::ReleaseAllRuntimeThreads method [.NET Framework hosting]
ms.assetid: 1a2995ff-5f02-4b49-84dc-3a5f9cfd7d55
topic_type:
- apiref
ms.openlocfilehash: bf551ccc2ae5bde3333dc8e3957099590a494dd3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709793"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a>Метод IDebuggerThreadControl::ReleaseAllRuntimeThreads

Уведомляет узел о том, что службы отладки собирается освободить все заблокированные потоки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a>Remarks  

 `ReleaseAllRuntimeThreads`Метод никогда не будет вызываться в потоке среды выполнения. Если в узле заблокирован поток среды выполнения, он должен освободить его сейчас.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IDebuggerThreadControl](idebuggerthreadcontrol-interface.md)
