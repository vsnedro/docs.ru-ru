---
description: 'Дополнительные сведения о: интерфейс ICorDebugChain'
title: Интерфейс ICorDebugChain
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
ms.openlocfilehash: 391c9a3e54d06d303728da5ab7f105bc8e2558ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661211"
---
# <a name="icordebugchain-interface"></a>Интерфейс ICorDebugChain

Представляет сегмент физического или логического стека вызовов.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumerateFrames](icordebugchain-enumerateframes-method.md)|Возвращает перечислитель, содержащий все управляемые кадры стека в цепочке, начиная с самого последнего кадра.|  
|[Метод GetActiveFrame](icordebugchain-getactiveframe-method.md)|Возвращает активный (то есть самый последний) кадр в цепочке.|  
|[Метод GetCallee](icordebugchain-getcallee-method.md)|Возвращает цепочку, вызванную этой цепочкой.|  
|[Метод GetCaller](icordebugchain-getcaller-method.md)|Возвращает цепочку, вызвавшую эту цепь.|  
|[Метод GetContext](icordebugchain-getcontext-method.md)|Не реализован.|  
|[Метод GetNext](icordebugchain-getnext-method.md)|Возвращает следующую цепь кадров для потока.|  
|[Метод GetPrevious](icordebugchain-getprevious-method.md)|Возвращает предыдущую цепочку кадров для потока.|  
|[Метод GetReason](icordebugchain-getreason-method.md)|Возвращает причину женесис данной вызывающей цепочки.|  
|[Метод GetRegisterSet](icordebugchain-getregisterset-method.md)|Возвращает набор регистров для активной части этой цепочки.|  
|[Метод GetStackRange](icordebugchain-getstackrange-method.md)|Возвращает диапазон адресов сегмента стека для этой цепочки.|  
|[Метод GetThread](icordebugchain-getthread-method.md)|Возвращает физический поток, частью которого является эта цепочка вызовов.|  
|[Метод IsManaged](icordebugchain-ismanaged-method.md)|Возвращает значение, указывающее, выполняется ли в этой цепочке управляемый код.|  
  
## <a name="remarks"></a>Remarks  

 Кадры стека в цепочке занимают непрерывное пространство стека и совместно используют один и тот же поток и контекст. Цепочка может представлять как управляемые, так и неуправляемые цепочки кода. Пустой `ICorDebugChain` экземпляр представляет собой неуправляемую цепочку кода.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
