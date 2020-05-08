---
title: Метод ICorDebugEval2::NewParameterizedObjectNoConstructor
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObjectNoConstructor
helpviewer_keywords:
- NewParameterizedObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObjectNoConstructor method [.NET Framework debugging]
ms.assetid: f15b5b78-94f4-4eb9-b3b3-a621272f357c
topic_type:
- apiref
ms.openlocfilehash: 90fce1710f97341fb49be1d07f7af2edf8cb848c
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976087"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="66811-102">Метод ICorDebugEval2::NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="66811-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>
<span data-ttu-id="66811-103">Создает новый объект параметризованного типа указанного класса без попытки вызова метода конструктора.</span><span class="sxs-lookup"><span data-stu-id="66811-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66811-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66811-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66811-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="66811-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="66811-106">окне Указатель на объект ICorDebugClass, представляющий класс объекта, для которого создается экземпляр.</span><span class="sxs-lookup"><span data-stu-id="66811-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="66811-107">окне Число переданных аргументов типа.</span><span class="sxs-lookup"><span data-stu-id="66811-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="66811-108">окне Массив указателей, каждый из которых указывает на объект ICorDebugType, представляющий аргумент типа для объекта, для которого создается экземпляр.</span><span class="sxs-lookup"><span data-stu-id="66811-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66811-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="66811-109">Remarks</span></span>  
 <span data-ttu-id="66811-110">`NewParameterizedObjectNoConstructor` Метод завершится ошибкой, если передается неверное число аргументов типа или неправильные типы аргументов типа.</span><span class="sxs-lookup"><span data-stu-id="66811-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66811-111">Требования</span><span class="sxs-lookup"><span data-stu-id="66811-111">Requirements</span></span>  
 <span data-ttu-id="66811-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66811-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66811-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66811-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66811-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66811-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66811-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66811-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
