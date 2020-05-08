---
title: Метод ICorDebugEval::CallFunction
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
ms.openlocfilehash: 1cf0080945ad78565fae3fedb454ceba7825cb4a
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976243"
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="326e9-102">Метод ICorDebugEval::CallFunction</span><span class="sxs-lookup"><span data-stu-id="326e9-102">ICorDebugEval::CallFunction Method</span></span>

<span data-ttu-id="326e9-103">Настраивает вызов указанной функции.</span><span class="sxs-lookup"><span data-stu-id="326e9-103">Sets up a call to the specified function.</span></span>

<span data-ttu-id="326e9-104">Этот метод является устаревшим в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="326e9-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="326e9-105">Вместо этого используйте [ICorDebugEval2:: каллпараметеризедфунктион](icordebugeval2-callparameterizedfunction-method.md) .</span><span class="sxs-lookup"><span data-stu-id="326e9-105">Use [ICorDebugEval2::CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="326e9-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="326e9-106">Syntax</span></span>

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a><span data-ttu-id="326e9-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="326e9-107">Parameters</span></span>

`pFunction`\
<span data-ttu-id="326e9-108">окне Указатель на объект ICorDebugFunction, указывающий вызываемую функцию.</span><span class="sxs-lookup"><span data-stu-id="326e9-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>

`nArgs`\
<span data-ttu-id="326e9-109">окне Число аргументов для функции.</span><span class="sxs-lookup"><span data-stu-id="326e9-109">[in] The number of arguments for the function.</span></span>

`ppArgs`\
<span data-ttu-id="326e9-110">окне Массив указателей, каждый из которых указывает на объект ICorDebugValue, указывающий аргумент, передаваемый в функцию.</span><span class="sxs-lookup"><span data-stu-id="326e9-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="326e9-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="326e9-111">Remarks</span></span>

<span data-ttu-id="326e9-112">Если функция является виртуальной, `CallFunction` выполняет виртуальную диспетчеризацию.</span><span class="sxs-lookup"><span data-stu-id="326e9-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="326e9-113">Если функция находится в другом домене приложения, произойдет переход, если все аргументы также находятся в этом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="326e9-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>

## <a name="requirements"></a><span data-ttu-id="326e9-114">Требования</span><span class="sxs-lookup"><span data-stu-id="326e9-114">Requirements</span></span>

<span data-ttu-id="326e9-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="326e9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="326e9-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="326e9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="326e9-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="326e9-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="326e9-118">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="326e9-118">**.NET Framework Versions:** 1.1, 1.0</span></span>

## <a name="see-also"></a><span data-ttu-id="326e9-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="326e9-119">See also</span></span>

- [<span data-ttu-id="326e9-120">Метод CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="326e9-120">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)
