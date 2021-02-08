---
description: 'Дополнительные сведения о методе: ICorDebugThread2:: Интерцепткуррентексцептион'
title: Метод ICorDebugThread2::InterceptCurrentException
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.InterceptCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::InterceptCurrentException
helpviewer_keywords:
- InterceptCurrentException method [.NET Framework debugging]
- ICorDebugThread2::InterceptCurrentException method [.NET Framework debugging]
ms.assetid: 536d2357-1b97-49e0-a10c-c860aed74e6e
topic_type:
- apiref
ms.openlocfilehash: 5bf8d3adf6f5e4a24d8fc5abddb72c0c8963c142
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790717"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a>Метод ICorDebugThread2::InterceptCurrentException

Позволяет отладчику перехватить текущее исключение в этом потоке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pFrame`  
 окне Указатель на объект ICorDebugFrame, представляющий активный кадр стека.  
  
## <a name="remarks"></a>Remarks  

 `InterceptCurrentException`Метод может быть вызван между обратным вызовом исключения ([ICorDebugManagedCallback:: Exception](icordebugmanagedcallback-exception-method.md) или [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md)) и связанным вызовом [ICorDebugController:: Continue](icordebugcontroller-continue-method.md).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
