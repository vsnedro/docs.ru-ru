---
title: Метод ICLRDataTarget::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
ms.openlocfilehash: 35b7bff5d4d778a429ddc1dcd0206e6e8970ee4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703503"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a>Метод ICLRDataTarget::GetThreadContext

Возвращает текущий контекст выполнения для данного потока в целевом процессе. Этот метод вызывается службами доступа к данным среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `threadID`  
 окне Идентификатор операционной системы потока в целевом процессе.  
  
 `contextFlags`  
 окне Флаги, указывающие, какие части контекста должны быть возвращены. Реализация возвратит по крайней мере эти части контекста.  
  
 `contextSize`  
 окне Размер контекста.  
  
 `context`  
 заполняет Указатель на буфер, в который будет помещен контекст.  
  
 Данные в `context` буфере должны быть в формате `CONTEXT` структуры Win32. Контекст задает зависящие от процессора данные регистров, поэтому определение `CONTEXT` структуры Win32 зависит от архитектуры процессора. Описание структуры Win32 см. в файле заголовка WinNT. h `CONTEXT` .  
  
## <a name="remarks"></a>Комментарии  

 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl, Клрдата. h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRDataTarget](iclrdatatarget-interface.md)
