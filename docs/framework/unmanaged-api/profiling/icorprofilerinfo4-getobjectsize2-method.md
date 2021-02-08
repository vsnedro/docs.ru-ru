---
description: 'Дополнительные сведения о методе: метод icorprofilerinfo4:: GetObjectSize2'
title: Метод ICorProfilerInfo4::GetObjectSize2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetObjectSize2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type:
- apiref
ms.openlocfilehash: 986c3d99501e21feec95dd3b6014f8d11d809704
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794528"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a>Метод ICorProfilerInfo4::GetObjectSize2

Возвращает размер указанного объекта. Заменяет метод [ICorProfilerInfo:: жетобжектсизе](icorprofilerinfo-getobjectsize-method.md) , сообщая размеры объектов, размер которых больше, чем может быть выражено в `ULONG` .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
## <a name="parameters"></a>Параметры  

 `objectId`  
 окне Идентификатор объекта.  
  
 `pcSize`  
 заполняет Указатель на размер объекта в байтах.  
  
## <a name="remarks"></a>Remarks  

 Различные объекты одних и тех же типов часто имеют одинаковый размер. Однако некоторые типы, такие как массивы или строки, могут иметь разные размеры для каждого объекта.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo4](icorprofilerinfo4-interface.md)
