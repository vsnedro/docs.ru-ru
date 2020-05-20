---
title: Метод ICorDebugRegisterSet2::GetRegisters
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type:
- apiref
ms.openlocfilehash: 71b9d59621efb547713cb4a6c9df7a7142f4a677
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615193"
---
# <a name="icordebugregisterset2getregisters-method"></a>Метод ICorDebugRegisterSet2::

Возвращает значение каждого регистра (для платформы, в которой код выполняется в данный момент), заданный заданной битовой маской.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>Параметры

 `maskCount`  
 окне Размер массива в байтах `mask` .  
  
 `mask`  
 окне Массив байтов, каждый бит которого соответствует регистру. Если бит равен 1, будет получено соответствующее значение регистра.  
  
 `regCount`  
 окне Число возвращаемых значений регистров.  
  
 `regBuffer`  
 заполняет Массив `CORDB_REGISTER` объектов, каждый из которых получает значение регистра.  
  
## <a name="remarks"></a>Комментарии

 `GetRegisters`Метод возвращает массив значений из регистров, заданных маской. Массив не содержит значений регистров, бит маски которых не задан. Таким `regBuffer` же размером массива должно быть значение, равное количеству 1 в маске. Если значение `regCount` слишком мало для количества регистров, указанных маской, значения более высоких регистров будут обрезаны из набора. Если `regCount` значение слишком велико, неиспользуемые `regBuffer` элементы будут неизменными.  
  
 Если недоступная ККМ обозначается маской, для этой регистрации будет возвращено неопределенное значение.  
  
 Этот `ICorDebugRegisterSet2::GetRegisters` метод необходим для платформ, имеющих более 64 регистров. Например, IA64 имеет 128 регистров общего назначения и 128 регистров с плавающей запятой, поэтому в битовой маске требуется более 64 бит.  
  
 Если у вас больше 64 регистров, как в случае с платформами, такими как x86, `GetRegisters` метод просто преобразует байты в `mask` массиве байтов в, `ULONG64` а затем вызывает метод [ICorDebugRegisterSet::](icordebugregisterset-getregisters-method.md) GetBytes, который принимает `ULONG64` маску.  
  
## <a name="requirements"></a>Требования

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейс ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
- [Интерфейс ICorDebugRegisterSet](icordebugregisterset-interface.md)
