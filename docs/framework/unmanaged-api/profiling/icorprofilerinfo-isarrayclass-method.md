---
title: Метод ICorProfilerInfo::IsArrayClass
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
ms.openlocfilehash: 2608f91a7c5baa935e48fbe58ad4d14aaaad1f0d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722509"
---
# <a name="icorprofilerinfoisarrayclass-method"></a>Метод ICorProfilerInfo::IsArrayClass

Определяет, является ли указанный класс классом массива.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a>Параметры  

 `classId`  
 окне Идентификатор анализируемого класса.  
  
 `pBaseElemType`  
 заполняет Указатель на значение перечисления Корелементтипе, указывающее тип элементов массива.  
  
 `pBaseClassId`  
 заполняет Указатель на идентификатор класса элементов массива, если он доступен.  
  
 `pcRank`  
 заполняет Указатель на целое число, указывающее ранг (то есть количество измерений) массива.  
  
## <a name="remarks"></a>Комментарии  

 Если указанный класс является классом массива, `IsArrayClass` метод возвращает S_OK HRESULT и значения для любых выходных параметров, отличных от NULL. В противном случае возвращается S_FALSE.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
