---
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
ms.openlocfilehash: 354df02b27e87550ba602fe102352455c227441b
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859690"
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
 окне `true` Если вы планируете запустить отладку Win32 или присоединиться с включенной отладкой Win32, передавайте значение. в противном `false`случае передайте.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если службы отладки определяют, что можно запустить новый процесс или присоединиться к заданному процессу, учитывая сведения о текущем компьютере и конфигурации среды выполнения. Возможные значения HRESULT:  
  
- S_OK  
  
- CORDBG_E_DEBUGGING_NOT_POSSIBLE  
  
- CORDBG_E_KERNEL_DEBUGGER_PRESENT  
  
- CORDBG_E_KERNEL_DEBUGGER_ENABLED  
  
## <a name="remarks"></a>Примечания  
 Этот метод является исключительно информационным. Интерфейс не будет останавливаться при запуске или присоединении к процессу, независимо от значения, возвращаемого `CanLaunchOrAttach`.  
  
 Если планируется запуск с включенной отладкой Win32 или подключение с включенной отладкой `true` Win32 `win32DebuggingEnabled`, передайте. Значение HRESULT, возвращаемое, `CanLaunchOrAttach` может отличаться при использовании этого параметра.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebug](icordebug-interface.md)
