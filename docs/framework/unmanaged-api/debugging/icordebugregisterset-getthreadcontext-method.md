---
title: Метод ICorDebugRegisterSet::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
ms.openlocfilehash: 04ae3c4dd663351eaf1a58646e24e8ae95aeb9ad
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378281"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a>Метод ICorDebugRegisterSet::GetThreadContext
Возвращает контекст текущего потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `contextSize`  
 окне Размер массива в байтах `context` .  
  
 `context`  
 [вход, выход] Массив байтов, образующих `CONTEXT` структуру Win32 для текущей платформы.  
  
## <a name="remarks"></a>Remarks  
 Отладчик должен вызвать эту функцию вместо `GetThreadContext` функции Win32, так как поток может находиться в состоянии "перехвачено", в котором его контекст был временно изменен. Возвращаемые данные представляют собой `CONTEXT` структуру Win32 для текущей платформы.  
  
 Для неконечных кадров клиенты должны проверить, какие регистры являются допустимыми с помощью [ICorDebugRegisterSet:: жетрегистерсаваилабле](icordebugregisterset-getregistersavailable-method.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugRegisterSet](icordebugregisterset-interface.md)
- [Интерфейс ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
