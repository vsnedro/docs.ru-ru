---
description: 'Дополнительные сведения о: интерфейс ICorDebugObjectValue'
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
ms.openlocfilehash: a2af438bbb4c2f56eb1a72151e339b6b0a978eec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794778"
---
# <a name="icordebugobjectvalue-interface"></a>Интерфейс ICorDebugObjectValue

Подкласс "ICorDebugValue", представляющий значение, которое содержит объект.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetClass](icordebugobjectvalue-getclass-method.md)|Возвращает указатель интерфейса на общеязыковую среду выполнения (CLR) <xref:System.Type> объекта, `ICorDebugObjectValue` на который ссылается эта ссылка.|  
|[Метод GetContext](icordebugobjectvalue-getcontext-method.md)|Не реализован.|  
|[Метод GetFieldValue](icordebugobjectvalue-getfieldvalue-method.md)|Возвращает указатель интерфейса на объект [ICorDebugValue](icordebugvalue-interface.md) , представляющий значение указанного поля указанного класса.|  
|[Метод GetManagedCopy](icordebugobjectvalue-getmanagedcopy-method.md)|Является устаревшей. Этот метод не следует вызывать.|  
|[Метод GetVirtualMethod](icordebugobjectvalue-getvirtualmethod-method.md)|Не реализован.|  
|[Метод IsValueClass](icordebugobjectvalue-isvalueclass-method.md)|Возвращает значение, указывающее, является ли объект, на который ссылается это, `ICorDebugObjectValue` типом значения.|  
|[Метод SetFromManagedCopy](icordebugobjectvalue-setfrommanagedcopy-method.md)|Является устаревшей. Этот метод не следует вызывать.|  
  
## <a name="remarks"></a>Remarks  

 `ICorDebugObjectValue`Остается действительным до тех пор, пока отлаживаемый процесс не будет продолжен.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
