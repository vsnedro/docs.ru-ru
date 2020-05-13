---
title: Метод ICorDebugModule2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type:
- apiref
ms.openlocfilehash: d5109043a8601d7997f52e88ea472644f1b9ca03
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208789"
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="0daf6-102">Метод ICorDebugModule2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="0daf6-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="0daf6-103">Устанавливает состояние Только мой код (JMC) всех методов всех классов данного ICorDebugModule2 в указанное значение, за исключением тех, `pTokens` которые в массиве задаются в противоположном значении.</span><span class="sxs-lookup"><span data-stu-id="0daf6-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0daf6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0daf6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0daf6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0daf6-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="0daf6-106">окне Задайте значение `true` , если код должен быть отлажен; в противном случае — значение `false` .</span><span class="sxs-lookup"><span data-stu-id="0daf6-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="0daf6-107">[in] Размер массива `pTokens`.</span><span class="sxs-lookup"><span data-stu-id="0daf6-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="0daf6-108">окне Массив `mdToken` значений, каждый из которых ссылается на метод, для которого в качестве его состояния JMC задано значение! `bIsJustMycode` .</span><span class="sxs-lookup"><span data-stu-id="0daf6-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0daf6-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="0daf6-109">Remarks</span></span>  
 <span data-ttu-id="0daf6-110">Состояние JMC каждого метода, указанного в `pTokens` массиве, устанавливается равным противоположному `bIsJustMycode` значению.</span><span class="sxs-lookup"><span data-stu-id="0daf6-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="0daf6-111">Состояние всех остальных методов этого модуля задается равным `bIsJustMycode` значению.</span><span class="sxs-lookup"><span data-stu-id="0daf6-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="0daf6-112">`SetJMCStatus`Метод удаляет все предыдущие параметры JMC в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="0daf6-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="0daf6-113">`SetJMCStatus`Метод возвращает S_OK HRESULT, если все функции заданы успешно.</span><span class="sxs-lookup"><span data-stu-id="0daf6-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="0daf6-114">Он возвращает CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT, если некоторые функции, которые помечены, `true` не могут быть отлажены.</span><span class="sxs-lookup"><span data-stu-id="0daf6-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0daf6-115">Требования</span><span class="sxs-lookup"><span data-stu-id="0daf6-115">Requirements</span></span>  
 <span data-ttu-id="0daf6-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0daf6-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0daf6-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0daf6-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0daf6-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0daf6-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0daf6-119">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0daf6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
