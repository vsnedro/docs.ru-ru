---
title: Метод ICorDebugProcess2::GetThreadForTaskID
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetThreadForTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetThreadForTaskID
helpviewer_keywords:
- ICorDebugProcess2::GetThreadForTaskId method [.NET Framework debugging]
- GetThreadForTaskID method [.NET Framework debugging]
ms.assetid: 32d54a5b-8ad3-405b-a1b9-0936a3b49d1e
topic_type:
- apiref
ms.openlocfilehash: 2b18289af460f64085fedd7b32387ebcb8c51715
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713552"
---
# <a name="icordebugprocess2getthreadfortaskid-method"></a>Метод ICorDebugProcess2::GetThreadForTaskID

Возвращает поток, в котором выполняются задачи с указанным идентификатором.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetThreadForTaskID (  
    [in]  TASKID            taskid,  
    [out] ICorDebugThread2  **ppThread  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `taskid`  
 окне Идентификатор задачи.  
  
 `ppThread`  
 заполняет Указатель на адрес объекта ICorDebugThread2, который представляет поток для извлечения.  
  
## <a name="remarks"></a>Комментарии  

 Узел может задать идентификатор задачи с помощью метода [ICLRTask:: SetTaskIdentifier](../hosting/iclrtask-settaskidentifier-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
