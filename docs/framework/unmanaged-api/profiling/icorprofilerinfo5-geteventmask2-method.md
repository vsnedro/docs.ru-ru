---
description: 'Дополнительные сведения о методе: ICorProfilerInfo5:: GetEventMask2'
title: Метод ICorProfilerInfo5::GetEventMask2
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerInfo5.GetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type:
- apiref
ms.openlocfilehash: c6652ffe1b8fd0d99ce5493c8ba27a971363c423
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646664"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a>Метод ICorProfilerInfo5::GetEventMask2

[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Получает текущие категории событий, о которых профилировщик хочет получать уведомления из среды CLR.  Он предоставляет функциональные возможности, не предоставляемые методом [ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pdwEventsLow`  
 [из] Указатель на 4-байтовое значение, определяющее категории событий. Каждый бит управляет отдельной возможностью, поведением или типом события. Биты описаны в перечислении [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .  
  
 `pdwEventsHigh`  
 [из] Указатель на 4-байтовое значение, определяющее категории событий.  Каждый бит управляет отдельной возможностью, поведением или типом события. Биты описаны в перечислении [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) .  
  
## <a name="remarks"></a>Remarks  

 Метод `GetEventMask2` используется для определения обратных вызовов, на которые подписался профилировщик. Обычно выполняется логическое или для `pdwEventsLow` значений и, а также `pdwEventsHigh` все новые биты, которые необходимо задать, а затем вызывается метод [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .  
  
 Этот метод является рекомендуемым альтернативой методу [GetEventMask](icorprofilerinfo-geteventmask-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo5](icorprofilerinfo5-interface.md)
- [Метод SetEventMask2](icorprofilerinfo5-seteventmask2-method.md)
