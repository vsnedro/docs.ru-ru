---
title: Метод ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: a175a6b6c91c284348580e1d9dc9ef0c5f5fc5df
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895121"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a>Метод ICorDebugAppDomain4::GetObjectForCCW
Возвращает управляемый объект из вызываемой оболочки COMr (CCW).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ccwPointer`  
 [in] Указатель вызываемой оболочки COM (CCW).  
  
 `ppManagedObject`  
 заполняет Указатель на адрес объекта ICorDebugValue, который представляет управляемый объект, соответствующий заданному указателю CCW.  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugAppDomain4](icordebugappdomain4-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
