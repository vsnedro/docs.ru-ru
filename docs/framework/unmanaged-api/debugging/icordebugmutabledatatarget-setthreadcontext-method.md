---
description: 'Дополнительные сведения о методе: Икордебугмутабледататаржет:: SetThreadContext'
title: Метод ICorDebugMutableDataTarget::SetThreadContext
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: 4674df92b72b44e19eff663c9a17dd8ca4b5a1b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722481"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a>Метод ICorDebugMutableDataTarget::SetThreadContext

Задает контекст (значения регистра) для потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwThreadID`  
 [in] Идентификатор потока, определяемый операционной системой.  
  
 `contextSize`  
 [in] Размер буфера `pContext` для записи.  
  
 `pContext`  
 [in] Указатель на байты, которые требуется записать.  
  
## <a name="remarks"></a>Remarks  

 Метод `SetThreadContext` обновляет текущий контекст для потока, указанного аргументом `dwThreadID`, который задается операционной системой. Формат записи контекста определяется платформой, указанной в методе [ICorDebugDataTarget::-Platform](icordebugdatatarget-getplatform-method.md) . В Windows это структура [контекста](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
