---
title: Интерфейс ICorDebugEval2
ms.date: 03/30/2017
api_name:
- ICorDebugEval2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2
helpviewer_keywords:
- ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type:
- apiref
ms.openlocfilehash: b597d95b5b25e5ebf04fac48e4f3fda312a9594c
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976126"
---
# <a name="icordebugeval2-interface"></a><span data-ttu-id="113b0-102">Интерфейс ICorDebugEval2</span><span class="sxs-lookup"><span data-stu-id="113b0-102">ICorDebugEval2 Interface</span></span>

<span data-ttu-id="113b0-103">Расширяет "ICorDebugEval" для обеспечения поддержки универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="113b0-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="113b0-104">Методы</span><span class="sxs-lookup"><span data-stu-id="113b0-104">Methods</span></span>  
  
|<span data-ttu-id="113b0-105">Метод</span><span class="sxs-lookup"><span data-stu-id="113b0-105">Method</span></span>|<span data-ttu-id="113b0-106">Описание</span><span class="sxs-lookup"><span data-stu-id="113b0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="113b0-107">Метод CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="113b0-107">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="113b0-108">Настраивает вызов указанного "ICorDebugFunction", который может быть вложен в тип, конструктор которого принимает параметры типа или сам может принимать параметры типа.</span><span class="sxs-lookup"><span data-stu-id="113b0-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="113b0-109">Метод CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="113b0-109">CreateValueForType Method</span></span>](icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="113b0-110">Возвращает указатель на новый "ICorDebugValue" указанного типа с начальным значением NULL или нулем.</span><span class="sxs-lookup"><span data-stu-id="113b0-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="113b0-111">Метод NewParameterizedArray</span><span class="sxs-lookup"><span data-stu-id="113b0-111">NewParameterizedArray Method</span></span>](icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="113b0-112">Выделяет новый массив указанного типа элемента и измерений.</span><span class="sxs-lookup"><span data-stu-id="113b0-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="113b0-113">Метод NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="113b0-113">NewParameterizedObject Method</span></span>](icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="113b0-114">Создает новый объект параметризованного типа и вызывает метод конструктора объекта.</span><span class="sxs-lookup"><span data-stu-id="113b0-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="113b0-115">Метод NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="113b0-115">NewParameterizedObjectNoConstructor Method</span></span>](icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="113b0-116">Создает новый объект параметризованного типа указанного класса без попытки вызова метода конструктора</span><span class="sxs-lookup"><span data-stu-id="113b0-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="113b0-117">Метод NewStringWithLength</span><span class="sxs-lookup"><span data-stu-id="113b0-117">NewStringWithLength Method</span></span>](icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="113b0-118">Создает новую строку указанной длины с указанным содержимым.</span><span class="sxs-lookup"><span data-stu-id="113b0-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="113b0-119">Метод RudeAbort</span><span class="sxs-lookup"><span data-stu-id="113b0-119">RudeAbort Method</span></span>](icordebugeval2-rudeabort-method.md)|<span data-ttu-id="113b0-120">Прерывает вычисление, `ICorDebugEval2` выполняемое в данный момент.</span><span class="sxs-lookup"><span data-stu-id="113b0-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="113b0-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="113b0-121">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="113b0-122">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="113b0-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="113b0-123">Требования</span><span class="sxs-lookup"><span data-stu-id="113b0-123">Requirements</span></span>  
 <span data-ttu-id="113b0-124">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="113b0-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="113b0-125">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="113b0-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="113b0-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="113b0-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="113b0-127">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="113b0-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="113b0-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="113b0-128">See also</span></span>

- [<span data-ttu-id="113b0-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="113b0-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
