---
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
ms.openlocfilehash: b18de87cf89985e0f7ec11edf58b43d67720251c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718024"
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
  
## <a name="remarks"></a>Комментарии  

 Тело метода в коде MSIL должен располагаться как относительный виртуальный адрес (RVA) относительно загруженного модуля. Это означает, что он следует за модулем в пределах 4 ГБ. Чтобы упростить средство для замены тела метода, `GetILFunctionBodyAllocator` метод обеспечивает выделение памяти в пределах этого диапазона.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
