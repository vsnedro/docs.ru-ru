---
title: Метод ICorProfilerInfo4::GetILToNativeMapping2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetILToNativeMapping2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2
helpviewer_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2 method [.NET Framework profiling]
- GetILToNativeMapping2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 756c1c25-08a7-4060-9798-dbeaa2f3bee5
topic_type:
- apiref
ms.openlocfilehash: 37d6b6d5112089df18fb138086db5e138a69629c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697757"
---
# <a name="icorprofilerinfo4getiltonativemapping2-method"></a>Метод ICorProfilerInfo4::GetILToNativeMapping2

Получает сопоставление из смещений MSIL в собственные смещения для кода, содержащегося в версии указанной функции, перекомпилированной с помощью JIT-компилятора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ReJITID reJitId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `functionId`  
 [in] Идентификатор функции, которая содержит код.  
  
 `pReJitId`  
 [in] Идентификатор функции, перекомпилированной с помощью JIT-компилятора. Удостоверение должно быть равно нулю в .NET Framework 4,5.  
  
 `cMap`  
 [in] Максимальный размер массива `map`.  
  
 `pcMap`  
 [out] Общее количество доступных структур COR_DEBUG_IL_TO_NATIVE_MAP.  
  
 `map`  
 [out] Массив структур `COR_DEBUG_IL_TO_NATIVE_MAP`, каждая из которых задает смещения. После возврата метода `GetILToNativeMapping2` параметр `map` будет содержать все или некоторые из структур `COR_DEBUG_IL_TO_NATIVE_MAP`.  
  
## <a name="remarks"></a>Комментарии  

 `GetILToNativeMapping2` аналогичен методу [ICorProfilerInfo:: GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) , за исключением того, что он позволяет профилировщику указать идентификатор перекомпилированной функции в будущих выпусках.  
  
> [!NOTE]
> Метод [икорпрофилерфунктионконтрол:: сетилинструментедкодемап](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) не реализован в .NET Framework 4,5, поэтому функции, которые были JIT-скомпилированы, не могут иметь сопоставление с IL-кодом, которое отличается от первоначально скомпилированной функции. Таким образом, `GetILToNativeMapping2` не может вызываться с ненулевым JIT-перекомпилированным идентификатором в .NET Framework 4,5.  
  
 Метод `GetILToNativeMapping2` возвращает массив структур `COR_DEBUG_IL_TO_NATIVE_MAP`. Чтобы убедиться, что определенные диапазоны машинных инструкций соответствуют специальным областям кода (например, прологу), в качестве поля в массиве можно `ilOffset` задать значение перечисления [кордебугилтонативемаппингтипес](../debugging/cordebugiltonativemappingtypes-enumeration.md) .  
  
 После возврата метода `GetILToNativeMapping2` необходимо убедиться, что буфер `map` был достаточно велик, чтобы вместить в себя все структуры `COR_DEBUG_IL_TO_NATIVE_MAP`. Для этого сравните значение параметра `cMap` со значением параметра `pcMap`. Если значение `pcMap`, умноженное на размер структуры `COR_DEBUG_IL_TO_NATIVE_MAP`COR_PRF_CODE_INFO, больше значения `cMap`, выделите буфер `map` большего размера, обновите параметр `cMap`, задав новый, больший размер, и вызовите метод `GetILToNativeMapping2` снова.  
  
 Кроме того, сначала можно вызвать метод `GetILToNativeMapping2` с буфером `map` нулевой длины для получения правильного размера буфера. Затем можно задать размер буфера равным значению, возвращенному в параметре `pcMap`, и вызвать метод `GetILToNativeMapping2` снова.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md)
- [Интерфейс ICorProfilerInfo4](icorprofilerinfo4-interface.md)
- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Профилирование](index.md)
