---
title: Интерфейс ICorDebugModule2
ms.date: 03/30/2017
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
ms.openlocfilehash: 7b98302985d9d54599ea8ea2e01dc2503c468d58
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210232"
---
# <a name="icordebugmodule2-interface"></a>Интерфейс ICorDebugModule2

Служит логическим расширением интерфейса ICorDebugModule.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ApplyChanges](icordebugmodule2-applychanges-method.md)|Применяет изменения в метаданных и изменения в коде промежуточного языка MSIL к выполняющемуся процессу.|  
|[Метод GetJITCompilerFlags](icordebugmodule2-getjitcompilerflags-method.md)|Возвращает флаги, управляющие JIT-компиляцией для этого `ICorDebugModule2` .|  
|[Метод ResolveAssembly](icordebugmodule2-resolveassembly-method.md)|Разрешает сборку, на которую ссылается указанный токен метаданных.|  
|[Метод SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md)|Задает флаги, управляющие JIT-компиляцией для этого `ICorDebugModule2` .|  
|[Метод SetJMCStatus](icordebugmodule2-setjmcstatus-method.md)|Устанавливает состояние Только мой код (JMC) всех методов всех классов в данном `ICorDebugModule2` значении, за исключением тех, которые заданы в `pTokens` массиве, для которого задано обратное значение.|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
