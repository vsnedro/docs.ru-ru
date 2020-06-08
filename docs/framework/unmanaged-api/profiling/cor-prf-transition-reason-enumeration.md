---
title: Перечисление COR_PRF_TRANSITION_REASON
ms.date: 03/30/2017
api_name:
- COR_PRF_TRANSITION_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_TRANSITION_REASON
helpviewer_keywords:
- COR_PRF_TRANSITION_REASON enumeration [.NET Framework profiling]
ms.assetid: da941118-01b7-4197-ae5b-9f2f8adcd623
topic_type:
- apiref
ms.openlocfilehash: e890c62a54654e86bb4a825613807efe142c8d5a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500745"
---
# <a name="cor_prf_transition_reason-enumeration"></a>Перечисление COR_PRF_TRANSITION_REASON
Указывает причину перехода из управляемого в неуправляемый код или наоборот.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|Переход происходит из-за вызова функции.|  
|`COR_PRF_TRANSITION_RETURN`|Переход происходит из-за возврата из функции.|  
  
## <a name="remarks"></a>Примечания  
 Когда происходит переход, профилировщик получает обратный вызов [ICorProfilerCallback:: манажедтаунманажедтранситион](icorprofilercallback-managedtounmanagedtransition-method.md) или [ICorProfilerCallback:: унманажедтоманажедтранситион](icorprofilercallback-unmanagedtomanagedtransition-method.md) , который предоставляет значение `COR_PRF_TRANSITION_REASON` перечисления для указания причины перехода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
