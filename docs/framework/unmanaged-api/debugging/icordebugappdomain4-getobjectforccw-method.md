---
description: 'Дополнительные сведения о методе: ICorDebugAppDomain4:: GetObjectForCCW'
title: Метод ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: 5ba4923c933d02f5d6ad5c1fd8c4d0e2ddb410d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754138"
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
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugAppDomain4](icordebugappdomain4-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
