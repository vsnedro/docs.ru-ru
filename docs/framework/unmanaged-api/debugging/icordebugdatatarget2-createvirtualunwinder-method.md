---
title: Метод ICorDebugDataTarget2::CreateVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
ms.openlocfilehash: 0967b1cda86eab35015279edeed9a6b9852036b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713942"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a>Метод ICorDebugDataTarget2::CreateVirtualUnwinder

Создает новый элемент очистки стека, запускающий операцию очистки, начиная с исходного контекста (который не обязательно является концом потока).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a>Параметры  

 nativeThreadID  
 [входной] Идентификатор собственного потока, стек которого должен быть очищен.  
  
 contextFlags  
 [входной] Флаги, указывающие, какие части контекста определены в `initialContext`.  
  
 cbContext  
 [входной] Размер `initialContext`.  
  
 initialContext  
 [входной] Данные в контексте.  
  
 ppUnwinder  
 [выходной] Указатель на адрес объекта интерфейса ICorDebugVirtualUnwinder.  
  
## <a name="return-value"></a>Возвращаемое значение  

 `S_OK` в случае успешного выполнения. Любое другое значение `HRESULT` указывает на ошибку. Любой сбой `HRESULT` , полученный mscordbi, считается неустранимым и приводит к возврату методов [ICorDebug](icordebug-interface.md) `CORDBG_E_DATA_TARGET_ERROR` .  
  
## <a name="remarks"></a>Комментарии  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugDataTarget2](icordebugdatatarget2-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
