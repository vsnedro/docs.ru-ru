---
description: 'Дополнительные сведения о методе: ICorDebugThread2:: GetTaskID'
title: Метод ICorDebugThread2::GetTaskID
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type:
- apiref
ms.openlocfilehash: 5429daee9150d63834c747dd5ebb763dd6f0da6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658689"
---
# <a name="icordebugthread2gettaskid-method"></a>Метод ICorDebugThread2::GetTaskID

Возвращает идентификатор задачи, выполняющейся в этом потоке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pTaskId`  
 заполняет Указатель на идентификатор задачи, выполняемой в потоке, представленном этим объектом ICorDebugThread2.  
  
## <a name="remarks"></a>Remarks  

 Задача может выполняться только в потоке, если поток связан с соединением. `GetTaskID` Возвращает ноль в `pTaskId` , если поток не связан с соединением.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
