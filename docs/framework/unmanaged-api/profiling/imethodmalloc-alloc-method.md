---
title: Метод IMethodMalloc::Alloc
ms.date: 03/30/2017
api_name:
- IMethodMalloc.Alloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type:
- apiref
ms.openlocfilehash: 58809f12e4dd4419b754caafc3f8b883b8bc5089
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721170"
---
# <a name="imethodmallocalloc-method"></a>Метод IMethodMalloc::Alloc

Пытается выделить указанный объем памяти для нового текста функции MSIL.

## <a name="syntax"></a>Синтаксис

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a>Параметры

`cb`\
окне Число байтов, которое необходимо выделить для тела метода.

## <a name="remarks"></a>Комментарии

 Выделенная память будет начинаться с адреса, превышающего базовый адрес модуля, связанного с этим распределителем. Иными словами, каждый распределитель создается для конкретного модуля и пытается выделить память с положительным смещением от его базового адреса. Если `Alloc` не удается выделить запрошенное число байтов по адресу, превышающему базовый адрес модуля, он возвращает E_OUTOFMEMORY, независимо от фактического объема доступной памяти.

 `Alloc`Метод следует использовать в сочетании с методом [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) .

## <a name="requirements"></a>Требования

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

 **Заголовок:** CorProf.idl, CorProf.h

 **Библиотека:** CorGuids.lib

 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>См. также раздел

- [Интерфейс IMethodMalloc](imethodmalloc-interface.md)
