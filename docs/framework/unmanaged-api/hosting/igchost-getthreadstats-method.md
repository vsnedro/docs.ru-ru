---
description: 'Дополнительные сведения о методе: IGCHost:: GetThreadStats'
title: Метод IGCHost::GetThreadStats
ms.date: 03/30/2017
api_name:
- IGCHost.GetThreadStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetThreadStats
helpviewer_keywords:
- IGCHost::GetThreadStats method [.NET Framework hosting]
- GetThreadStats method [.NET Framework hosting]
ms.assetid: 826baa9b-9218-4736-a509-7ab193b125a0
topic_type:
- apiref
ms.openlocfilehash: 2d923560e915a0c88035caad70ad91149d793cb8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709663"
---
# <a name="igchostgetthreadstats-method"></a>Метод IGCHost::GetThreadStats

Возвращает статистику по потокам для сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pFiberCookie`  
 окне Указатель на волокный файл cookie, указывающий поток, для которого необходимо получить статистику.  
  
 `pStats`  
 [вход, выход] Указатель на структуру [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) , содержащую статистику сборки мусора для указанного потока.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Гчост. idl, Гчост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IGCHost](igchost-interface.md)
