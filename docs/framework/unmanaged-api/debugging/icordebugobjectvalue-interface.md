---
title: Интерфейс ICorDebugObjectValue
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
ms.openlocfilehash: 603ab20b57dc4ba736b0342797d0be649a5bebc4
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207483"
---
# <a name="icordebugobjectvalue-interface"></a>Интерфейс ICorDebugObjectValue

Подкласс "ICorDebugValue", представляющий значение, которое содержит объект.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetClass](icordebugobjectvalue-getclass-method.md)|Возвращает указатель интерфейса на общеязыковую среду выполнения (CLR) <xref:System.Type> объекта, `ICorDebugObjectValue` на который ссылается эта ссылка.|  
|[Метод GetContext](icordebugobjectvalue-getcontext-method.md)|Не реализовано.|  
|[Метод GetFieldValue](icordebugobjectvalue-getfieldvalue-method.md)|Возвращает указатель интерфейса на объект [ICorDebugValue](icordebugvalue-interface.md) , представляющий значение указанного поля указанного класса.|  
|[Метод GetManagedCopy](icordebugobjectvalue-getmanagedcopy-method.md)|Устаревшее. Этот метод не следует вызывать.|  
|[Метод GetVirtualMethod](icordebugobjectvalue-getvirtualmethod-method.md)|Не реализовано.|  
|[Метод IsValueClass](icordebugobjectvalue-isvalueclass-method.md)|Возвращает значение, указывающее, является ли объект, на который ссылается это, `ICorDebugObjectValue` типом значения.|  
|[Метод SetFromManagedCopy](icordebugobjectvalue-setfrommanagedcopy-method.md)|Устаревшее. Этот метод не следует вызывать.|  
  
## <a name="remarks"></a>Remarks  
 `ICorDebugObjectValue`Остается действительным до тех пор, пока отлаживаемый процесс не будет продолжен.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
