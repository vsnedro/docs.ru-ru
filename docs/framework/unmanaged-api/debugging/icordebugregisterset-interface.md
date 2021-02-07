---
description: 'Дополнительные сведения о: интерфейс ICorDebugRegisterSet'
title: Интерфейс ICorDebugRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
ms.openlocfilehash: 7d888e9e395e9f5fa88c6a6d96b2b8e3171ef4ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690786"
---
# <a name="icordebugregisterset-interface"></a>Интерфейс ICorDebugRegisterSet

Представляет набор регистров, доступных на компьютере, который выполняет код в данный момент.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetRegisters](icordebugregisterset-getregisters-method.md)|Возвращает значение каждого регистра (на компьютере, выполняющем в данный момент код), который задается битовой маской.|  
|[Метод GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md)|Возвращает битовую маску, указывающую, какие регистры в данный `ICorDebugRegisterSet` момент доступны.|  
|[Метод GetThreadContext](icordebugregisterset-getthreadcontext-method.md)|Возвращает контекст текущего потока.|  
|[Метод SetRegisters](icordebugregisterset-setregisters-method.md)|Не реализовано для платформа .NET Framework версии 2,0.|  
|[Метод SetThreadContext](icordebugregisterset-setthreadcontext-method.md)|Не реализовано для платформа .NET Framework 2,0.|  
  
## <a name="remarks"></a>Remarks  

 `ICorDebugRegisterSet`Интерфейс поддерживает только 32-разрядные регистры. Используйте интерфейс [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) на платформах, таких как IA-64, требующих дополнительных регистров.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Интерфейс ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
