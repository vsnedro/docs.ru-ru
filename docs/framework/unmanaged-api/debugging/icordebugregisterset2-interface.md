---
description: 'Дополнительные сведения о: Интерфейс ICorDebugRegisterSet2'
title: Интерфейс ICorDebugRegisterSet2
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2
helpviewer_keywords:
- ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type:
- apiref
ms.openlocfilehash: 3501325df188879f5687347ef329f490b487d9d8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803611"
---
# <a name="icordebugregisterset2-interface"></a>Интерфейс ICorDebugRegisterSet2

Расширяет возможности интерфейса [ICorDebugRegisterSet](icordebugregisterset-interface.md) для аппаратных платформ, имеющих более 64 регистров.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetRegisters](icordebugregisterset2-getregisters-method.md)|Возвращает значение каждого регистра (на компьютере, выполняющем в данный момент код), который задается битовой маской.|  
|[Метод GetRegistersAvailable](icordebugregisterset2-getregistersavailable-method.md)|Возвращает массив байтов, предоставляющий битовую карту доступных регистров.|  
|[Метод SetRegisters](icordebugregisterset2-setregisters-method.md)|Не реализовано в платформа .NET Framework версии 2,0.|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Интерфейс ICorDebugRegisterSet](icordebugregisterset-interface.md)
