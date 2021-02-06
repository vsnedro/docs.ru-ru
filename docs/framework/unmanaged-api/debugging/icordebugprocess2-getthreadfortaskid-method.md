---
description: 'Дополнительные сведения о методе: ICorDebugProcess2:: Жетсреадфортаскид'
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
ms.openlocfilehash: aafb1223f6e2e73aae600fd482c76b84c57dae52
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650135"
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
  
## <a name="remarks"></a>Remarks  

 Узел может задать идентификатор задачи с помощью метода [ICLRTask:: SetTaskIdentifier](../hosting/iclrtask-settaskidentifier-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
