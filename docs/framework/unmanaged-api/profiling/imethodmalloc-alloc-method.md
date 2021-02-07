---
description: 'Дополнительные сведения о методе: IMethodMalloc:: Alloc'
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
ms.openlocfilehash: f8a41530e0e1a126fafa1816e6fed58d10df6587
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736958"
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

## <a name="remarks"></a>Remarks

 Выделенная память будет начинаться с адреса, превышающего базовый адрес модуля, связанного с этим распределителем. Иными словами, каждый распределитель создается для конкретного модуля и пытается выделить память с положительным смещением от его базового адреса. Если `Alloc` не удается выделить запрошенное число байтов по адресу, превышающему базовый адрес модуля, он возвращает E_OUTOFMEMORY, независимо от фактического объема доступной памяти.

 `Alloc`Метод следует использовать в сочетании с методом [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) .

## <a name="requirements"></a>Требования

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

 **Заголовок:** CorProf.idl, CorProf.h

 **Библиотека:** CorGuids.lib

 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс IMethodMalloc](imethodmalloc-interface.md)
