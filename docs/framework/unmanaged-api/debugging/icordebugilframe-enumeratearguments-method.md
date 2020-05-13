---
title: Метод ICorDebugILFrame::EnumerateArguments
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
ms.openlocfilehash: 3945b1dea62dc0616d669356faf60f0d09cfb084
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210310"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="e0dd5-102">Метод ICorDebugILFrame::EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="e0dd5-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="e0dd5-103">Возвращает перечислитель для аргументов в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0dd5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0dd5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0dd5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0dd5-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="e0dd5-106">заполняет Указатель на адрес объекта ICorDebugValueEnum, который является перечислителем для аргументов в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0dd5-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e0dd5-107">Remarks</span></span>  
 <span data-ttu-id="e0dd5-108">`EnumerateArguments`Возвращает перечислитель, который может перечислить аргументы, доступные в кадре вызова, представленном этим объектом ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="e0dd5-109">Список будет содержать аргументы [vararg](/cpp/windows/vararg) (то есть переменное число аргументов), а также аргументы, которые не являются аргументами `vararg` .</span><span class="sxs-lookup"><span data-stu-id="e0dd5-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0dd5-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e0dd5-110">Requirements</span></span>  
 <span data-ttu-id="e0dd5-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0dd5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0dd5-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0dd5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0dd5-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0dd5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0dd5-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0dd5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
