---
description: 'Дополнительные сведения: метод ICorDebug:: CanLaunchOrAttach'
title: Метод ICorDebug::CanLaunchOrAttach
ms.date: 03/30/2017
api_name:
- ICorDebug.CanLaunchOrAttach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type:
- apiref
ms.openlocfilehash: cb813c4bae968941de731d9d5b74d8f804b3c8ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723248"
---
# <a name="icordebugcanlaunchorattach-method"></a>Метод ICorDebug::CanLaunchOrAttach

Возвращает значение HRESULT, указывающее, возможен ли запуск нового процесса или присоединение к указанному существующему процессу в контексте текущего компьютера и конфигурации среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwProcessId`  
 окне Идентификатор существующего процесса.  
  
 `win32DebuggingEnabled`  
 окне `true` Если вы планируете запустить отладку Win32 или присоединиться с включенной отладкой Win32, войдите в. в противном случае передайте `false` .  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если службы отладки определяют, что можно запустить новый процесс или присоединиться к заданному процессу, учитывая сведения о текущем компьютере и конфигурации среды выполнения. Возможные значения HRESULT:  
  
- S_OK  
  
- CORDBG_E_DEBUGGING_NOT_POSSIBLE  
  
- CORDBG_E_KERNEL_DEBUGGER_PRESENT  
  
- CORDBG_E_KERNEL_DEBUGGER_ENABLED  
  
## <a name="remarks"></a>Remarks  

 Этот метод является исключительно информационным. Интерфейс не будет останавливаться при запуске или присоединении к процессу, независимо от значения, возвращаемого `CanLaunchOrAttach` .  
  
 Если планируется запуск с включенной отладкой Win32 или подключение с включенной отладкой Win32, передайте `true` `win32DebuggingEnabled` . Значение HRESULT, возвращаемое, `CanLaunchOrAttach` может отличаться при использовании этого параметра.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebug](icordebug-interface.md)
