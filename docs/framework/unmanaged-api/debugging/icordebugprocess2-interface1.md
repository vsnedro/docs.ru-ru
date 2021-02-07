---
description: 'Дополнительные сведения о: интерфейс ICorDebugProcess2'
title: Интерфейс ICorDebugProcess2
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2
helpviewer_keywords:
- ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type:
- apiref
ms.openlocfilehash: 47e94ee8ee4f45e365fa9efe888cb706f8bb1dfd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746598"
---
# <a name="icordebugprocess2-interface"></a>Интерфейс ICorDebugProcess2

Логическое расширение интерфейса ICorDebugProcess, представляющее процесс, выполняющий управляемый код.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ClearUnmanagedBreakpoint](icordebugprocess2-clearunmanagedbreakpoint-method.md)|Удаляет точку останова с указанным смещением, которое было задано предыдущим вызовом метода `ICorDebugProcess2::SetUnmanagedBreakpoint` .|  
|[Метод GetDesiredNGENCompilerFlags](icordebugprocess2-getdesiredngencompilerflags-method.md)|Возвращает флаги, которые должны быть установлены в среде CLR для загрузки изображения в процесс, на который ссылается this `ICorDebugProcess2` .|  
|[Метод GetReferenceValueFromGCHandle](icordebugprocess2-getreferencevaluefromgchandle-method.md)|Возвращает указатель ссылки на указанный управляемый объект, который имеет обработчик сборки мусора.|  
|[Метод GetThreadForTaskID](icordebugprocess2-getthreadfortaskid-method.md)|Возвращает поток, в котором выполняется задача с указанным идентификатором.|  
|[Метод GetVersion](icordebugprocess2-getversion-method.md)|Возвращает версию среды CLR, на основе которой выполняется отлаживаемый процесс.|  
|[Метод SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md)|Задает флаги, которые требуются для JIT-компилятора при загрузке изображения в отлаживаемый процесс.|  
|[Метод SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md)|Задает неуправляемую точку останова в указанном смещении машинного образа.|  
  
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
