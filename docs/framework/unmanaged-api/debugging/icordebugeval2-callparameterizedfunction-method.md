---
title: Метод ICorDebugEval2::CallParameterizedFunction
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CallParameterizedFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type:
- apiref
ms.openlocfilehash: 72bcc2479f7b6f41b384fc2517f0b04694663398
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976152"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a><span data-ttu-id="9d623-102">Метод ICorDebugEval2::CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="9d623-102">ICorDebugEval2::CallParameterizedFunction Method</span></span>
<span data-ttu-id="9d623-103">Настраивает вызов указанного ICorDebugFunction, который может быть вложен в класс, конструктор которого принимает <xref:System.Type> параметры или сам может принимать <xref:System.Type> параметры.</span><span class="sxs-lookup"><span data-stu-id="9d623-103">Sets up a call to the specified ICorDebugFunction, which can be nested inside a class whose constructor takes <xref:System.Type> parameters, or can itself take <xref:System.Type> parameters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d623-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d623-104">Syntax</span></span>  
  
```cpp  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d623-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9d623-105">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="9d623-106">окне Указатель на `ICorDebugFunction` объект, представляющий вызываемую функцию.</span><span class="sxs-lookup"><span data-stu-id="9d623-106">[in] A pointer to an `ICorDebugFunction` object that represents the function to be called.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="9d623-107">окне Число аргументов, которые принимает функция.</span><span class="sxs-lookup"><span data-stu-id="9d623-107">[in] The number of arguments that the function takes.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="9d623-108">окне Массив указателей, каждый из которых указывает на объект ICorDebugType, представляющий аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="9d623-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a function argument.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="9d623-109">окне Количество значений, переданных функции.</span><span class="sxs-lookup"><span data-stu-id="9d623-109">[in] The number of values passed in the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="9d623-110">окне Массив указателей, каждый из которых указывает на объект ICorDebugValue, представляющий значение, передаваемое в аргументе функции.</span><span class="sxs-lookup"><span data-stu-id="9d623-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents a value passed in a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d623-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="9d623-111">Remarks</span></span>  
 <span data-ttu-id="9d623-112">`CallParameterizedFunction`имеет вид [ICorDebugEval:: CallFunction](icordebugeval-callfunction-method.md) , за исключением того, что функция может находиться внутри класса с параметрами типа, может иметь параметры типа или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="9d623-112">`CallParameterizedFunction` is like [ICorDebugEval::CallFunction](icordebugeval-callfunction-method.md) except that the function may be inside a class with type parameters, may itself take type parameters, or both.</span></span> <span data-ttu-id="9d623-113">Аргументы типа должны быть даны сначала для класса, а затем для функции.</span><span class="sxs-lookup"><span data-stu-id="9d623-113">The type arguments should be given first for the class, and then for the function.</span></span>  
  
 <span data-ttu-id="9d623-114">Если функция находится в другом домене приложения, произойдет переход.</span><span class="sxs-lookup"><span data-stu-id="9d623-114">If the function is in a different application domain, a transition will occur.</span></span> <span data-ttu-id="9d623-115">Однако все аргументы типа и значения должны находиться в целевом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="9d623-115">However, all type and value arguments must be in the target application domain.</span></span>  
  
 <span data-ttu-id="9d623-116">Вычисление функций может выполняться только в ограниченных сценариях.</span><span class="sxs-lookup"><span data-stu-id="9d623-116">Function evaluation can be performed only in limited scenarios.</span></span> <span data-ttu-id="9d623-117">Если `CallParameterizedFunction` или `ICorDebugEval::CallFunction` завершается ошибкой, возвращаемое значение HRESULT будет указывать на наиболее общую возможную причину сбоя.</span><span class="sxs-lookup"><span data-stu-id="9d623-117">If `CallParameterizedFunction` or `ICorDebugEval::CallFunction` fails, the returned HRESULT will indicate the most general possible reason for failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d623-118">Требования</span><span class="sxs-lookup"><span data-stu-id="9d623-118">Requirements</span></span>  
 <span data-ttu-id="9d623-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d623-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d623-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d623-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d623-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d623-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d623-122">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d623-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
