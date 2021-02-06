---
description: 'Дополнительные сведения о методе ICorProfilerInfo:: GetILFunctionBodyAllocator'
title: Метод ICorProfilerInfo::GetILFunctionBodyAllocator
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
ms.openlocfilehash: 25d059d784fe64231d4d2ff3d23b4820443873cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647431"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a>Метод ICorProfilerInfo::GetILFunctionBodyAllocator

Возвращает интерфейс, предоставляющий метод для выделения памяти, используемой для перекачки тела метода в коде на языке MSIL.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a>Параметры  

 `moduleId`  
 окне Идентификатор модуля, в котором находится метод.  
  
 `ppMalloc`  
 заполняет Указатель на интерфейс [IMethodMalloc](imethodmalloc-interface.md) , предоставляющий метод для выделения памяти.  
  
## <a name="remarks"></a>Remarks  

 Тело метода в коде MSIL должен располагаться как относительный виртуальный адрес (RVA) относительно загруженного модуля. Это означает, что он следует за модулем в пределах 4 ГБ. Чтобы упростить средство для замены тела метода, `GetILFunctionBodyAllocator` метод обеспечивает выделение памяти в пределах этого диапазона.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
