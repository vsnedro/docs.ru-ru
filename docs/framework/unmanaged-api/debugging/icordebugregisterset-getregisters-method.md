---
description: См. Дополнительные сведения о методе ICorDebugRegisterSet::, регистрирующих
title: Метод ICorDebugRegisterSet::GetRegisters
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
ms.openlocfilehash: efb0f19fe9eb823912203b82267803739fc3e2cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690851"
---
# <a name="icordebugregistersetgetregisters-method"></a>Метод ICorDebugRegisterSet::GetRegisters

Возвращает значение каждого регистра (на компьютере, выполняющем в данный момент код), который задается битовой маской.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `mask`  
 окне Битовая маска, указывающая, какие значения регистров должны быть извлечены. Каждый бит соответствует регистру. Если бит задан равным 1, то значение регистра извлекается; в противном случае значение регистра не извлекается.  
  
 `regCount`  
 окне Число возвращаемых значений регистров.  
  
 `regBuffer`  
 заполняет Массив `CORDB_REGISTER` объектов, каждый из которых получает значение регистра.  
  
## <a name="remarks"></a>Remarks  

 Размер массива должен быть равен числу битов, равным одному в битовой маске. `regCount`Параметр задает количество элементов в буфере, которые будут принимать значения регистров. Если `regCount` значение слишком мало для количества регистров, указанных маской, то более высокие числовые регистры будут обрезаны из набора. Если `regCount` значение слишком велико, неиспользуемые `regBuffer` элементы будут неизменными.  
  
 Если битовая маска указывает недоступный регистр, `GetRegisters` возвращает неопределенное значение для этого регистра.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugRegisterSet](icordebugregisterset-interface.md)
- [Интерфейс ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
