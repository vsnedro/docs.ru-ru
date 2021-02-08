---
description: 'Дополнительные сведения о: интерфейс ICorDebugHeapValue'
title: Интерфейс ICorDebugHeapValue
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue
helpviewer_keywords:
- ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type:
- apiref
ms.openlocfilehash: 7c65cbce530f0d1f00d8610031fb604a0118ee29
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803689"
---
# <a name="icordebugheapvalue-interface"></a>Интерфейс ICorDebugHeapValue

Подкласс "ICorDebugValue", представляющий объект, собранный сборщиком мусора среды CLR.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateRelocBreakpoint](icordebugheapvalue-createrelocbreakpoint-method.md)|Не реализован.|  
|[Метод IsValid](icordebugheapvalue-isvalid-method.md)|Возвращает значение, указывающее, является ли объект, представленный этим объектом `ICorDebugHeapValue` , допустимым или освобожденным сборщиком мусора. Этот метод не рекомендуется к использованию в платформа .NET Framework версии 2,0.|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
