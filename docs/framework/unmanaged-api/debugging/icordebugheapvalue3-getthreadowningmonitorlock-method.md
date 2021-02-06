---
description: 'Дополнительные сведения о методе: ICorDebugHeapValue3:: Жетсреадовнингмониторлокк'
title: Метод ICorDebugHeapValue3::GetThreadOwningMonitorLock
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type:
- apiref
ms.openlocfilehash: 9bd9e251c1e04bffd749c0569e4716d4c6fa89e5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660704"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a>Метод ICorDebugHeapValue3::GetThreadOwningMonitorLock

Возвращает управляемый поток, которому принадлежит блокировка монитора для этого объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppThread`  
 заполняет Управляемый поток, которому принадлежит блокировка монитора для этого объекта.  
  
 `pAcquisitionCount`  
 заполняет Количество случаев, в течение которых этот поток должен снять блокировку, прежде чем возвратить его в качестве владельца.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|S_FALSE|Ни один управляемый поток не владеет блокировкой монитора для этого объекта.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Remarks  

 Если управляемый поток владеет блокировкой монитора для этого объекта:  
  
- Метод возвращает S_OK.  
  
- Объект потока действителен до тех пор, пока поток не завершит работу.  
  
 Если ни один управляемый поток не владеет блокировкой монитора для этого объекта `ppThread` и `pAcquisitionCount` не изменяется, а метод возвращает S_FALSE.  
  
 Если `ppThread` или не `pAcquisitionCount` является допустимым указателем, результат не определен.  
  
 Если возникает ошибка, которая не может определить, какой поток владеет блокировкой монитора для этого объекта, метод возвращает значение HRESULT, которое указывает на сбой.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
