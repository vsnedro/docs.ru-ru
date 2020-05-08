---
title: Метод ICorDebugEval2::CreateValueForType
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CreateValueForType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type:
- apiref
ms.openlocfilehash: fd7acaa8bcb4d53893855bcd25ff68cf26e30354
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976165"
---
# <a name="icordebugeval2createvaluefortype-method"></a><span data-ttu-id="a3a7f-102">Метод ICorDebugEval2::CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="a3a7f-102">ICorDebugEval2::CreateValueForType Method</span></span>
<span data-ttu-id="a3a7f-103">Возвращает указатель на новый объект ICorDebugValue указанного типа с начальным значением нуль или null.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-103">Gets a pointer to a new ICorDebugValue of the specified type, with an initial value of zero or null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3a7f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a3a7f-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3a7f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a3a7f-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="a3a7f-106">окне Указатель на объект ICorDebugType, представляющий тип.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-106">[in] Pointer to an ICorDebugType object that represents the type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="a3a7f-107">заполняет Указатель на адрес `ICorDebugValue` объекта, представляющий значение.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-107">[out] Pointer to the address of an `ICorDebugValue` object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3a7f-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="a3a7f-108">Remarks</span></span>  
 <span data-ttu-id="a3a7f-109">`CreateValueForType`обобщает [ICorDebugEval:: креатевалуе](icordebugeval-createvalue-method.md) , позволяя указать произвольный тип объекта, включая сконструированные типы, такие `List<int>`как.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-109">`CreateValueForType` generalizes [ICorDebugEval::CreateValue](icordebugeval-createvalue-method.md) by allowing you to specify an arbitrary object type, including constructed types such as `List<int>`.</span></span> <span data-ttu-id="a3a7f-110">Единственная цель этого метода — создать значение, которое может быть передано в вычисление функции.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-110">The only purpose of this method is to generate a value that can be passed to a function evaluation.</span></span>  
  
 <span data-ttu-id="a3a7f-111">Тип должен быть классом или типом значения.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-111">The type must be a class or a value type.</span></span> <span data-ttu-id="a3a7f-112">Этот метод нельзя использовать для создания значений массива или строковых значений.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-112">You cannot use this method to create array values or string values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3a7f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="a3a7f-113">Requirements</span></span>  
 <span data-ttu-id="a3a7f-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3a7f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3a7f-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3a7f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3a7f-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3a7f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3a7f-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3a7f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
