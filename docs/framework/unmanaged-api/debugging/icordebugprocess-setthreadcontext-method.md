---
title: Метод ICorDebugProcess::SetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type:
- apiref
ms.openlocfilehash: 5b4052485a6d420eb83578d135ce51f8a918aab0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724524"
---
# <a name="icordebugprocesssetthreadcontext-method"></a>Метод ICorDebugProcess::SetThreadContext

Задает контекст для данного потока в этом процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `threadID`  
 окне Идентификатор потока, для которого задается контекст.  
  
 `contextSize`  
 [in] Размер массива `context`.  
  
 `context`  
 окне Массив байтов, описывающих контекст потока.  
  
 Контекст указывает архитектуру процессора, на котором работает поток.  
  
## <a name="remarks"></a>Комментарии  

 Отладчик должен вызывать этот метод, а не `SetThreadContext` функцию Win32, так как поток может находиться в состоянии "перехвачено", в котором его контекст был временно изменен. Этот метод следует использовать только в том случае, если поток находится в машинном коде. Используйте [ICorDebugRegisterSet](icordebugregisterset-interface.md) для потоков в управляемом коде. Никогда не нужно изменять контекст потока во время события нестандартного управления (OOB).  
  
 Передаваемые данные должны быть структурой контекста для текущей платформы.  
  
 Этот метод может повредить среду выполнения при неправильном использовании.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
