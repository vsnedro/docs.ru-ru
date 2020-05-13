---
title: Интерфейс ICorDebugHandleValue
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue
helpviewer_keywords:
- ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type:
- apiref
ms.openlocfilehash: c901e21521e941c51939958175a5316808890e9f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208646"
---
# <a name="icordebughandlevalue-interface"></a>Интерфейс ICorDebugHandleValue

Подкласс ICorDebugReferenceValue, представляющий ссылочное значение, в котором отладчик создал маркер для сборки мусора.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Dispose](icordebughandlevalue-dispose-method.md)|Освобождает дескриптор, на который ссылается этот `ICorDebugHandleValue` объект, без явного освобождения указателя интерфейса.|  
|[Метод GetHandleType](icordebughandlevalue-gethandletype-method.md)|Возвращает значение Кордебугхандлетипе, описывающее тип маркера, на который ссылается this `ICorDebugHandleValue` .|  
  
## <a name="remarks"></a>Remarks  
 `ICorDebugReferenceValue`Объект становится недействительным при прерывании выполнения отлаживаемого кода. `ICorDebugHandleValue`Сохраняет ссылку на разрывы и продолжения до тех пор, пока он не будет явно освобожден.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
