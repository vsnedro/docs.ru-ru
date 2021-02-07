---
description: 'Дополнительные сведения о методе: ICorProfilerInfo2:: Жетбокскласслайаут'
title: Метод ICorProfilerInfo2::GetBoxClassLayout
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
ms.openlocfilehash: 0bc9ccc80da8bcc89cfe73eaa240310c01e6ca8f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760522"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a>Метод ICorProfilerInfo2::GetBoxClassLayout

Возвращает сведения о расположении указанного типа значения при его упаковке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a>Параметры  

 `classId`  
 окне Идентификатор класса, который описывает упакованный тип значения.  
  
 `pBufferOffset`  
 заполняет Целое число, которое является смещением относительно указателя на идентификатор упакованного объекта для типа значения.  
  
## <a name="remarks"></a>Remarks  

 `pBufferOffset`Значение — это расположение типа значения в поле. После `pBufferOffset` применения к упакованному объекту можно использовать макет класса типа значения для интерпретации значения объекта.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](icorprofilerinfo2-interface.md)
