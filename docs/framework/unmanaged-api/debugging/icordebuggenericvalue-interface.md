---
title: Интерфейс ICorDebugGenericValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
ms.openlocfilehash: 7c5359ddf2c021f77ad1ea0a8579316c3c773fd5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209790"
---
# <a name="icordebuggenericvalue-interface"></a>Интерфейс ICorDebugGenericValue

Подкласс "ICorDebugValue", который применяется ко всем значениям. Этот интерфейс предоставляет для значения методы Get и Set.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetValue](icordebuggenericvalue-getvalue-method.md)|Копирует значение в указанный буфер.|  
|[Метод SetValue](icordebuggenericvalue-setvalue-method.md)|Копирует новое значение из указанного буфера.|  
  
## <a name="remarks"></a>Remarks  
 `ICorDebugGenericValue`является подинтерфейсом, так как он не является удаленным.  
  
 Для ссылочных типов значение является ссылкой, а не содержимым ссылки.  
  
 Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
