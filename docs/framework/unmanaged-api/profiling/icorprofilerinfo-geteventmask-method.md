---
title: Метод ICorProfilerInfo::GetEventMask
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetEventMask
helpviewer_keywords:
- GetEventMask method [.NET Framework profiling]
- ICorProfilerInfo::GetEventMask method [.NET Framework profiling]
ms.assetid: ec34cc13-45a3-4695-abc3-b3347d4e6fc2
topic_type:
- apiref
ms.openlocfilehash: 16bd8b09d5118171e669e9c428fb444384b5867d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722574"
---
# <a name="icorprofilerinfogeteventmask-method"></a>Метод ICorProfilerInfo::GetEventMask

Получает текущие категории событий, о которых профилировщик хочет получать уведомления из среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetEventMask(  
    [out] DWORD *pdwEvents);  
```  
  
## <a name="parameters"></a>Параметры  

 `pdwEvents`  
 [из] Указатель на 4-байтовое значение, определяющее категории событий. Каждый бит управляет отдельной возможностью, поведением или типом события. Биты описаны в перечислении [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .  
  
## <a name="remarks"></a>Комментарии  
  
> [!NOTE]
> Вместо этого метода следует вызвать метод [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) . Несмотря на то `SetEventMask` , что метод поддерживается, [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) предоставляет дополнительные функциональные возможности.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод GetEventMask2](icorprofilerinfo5-geteventmask2-method.md)
- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
