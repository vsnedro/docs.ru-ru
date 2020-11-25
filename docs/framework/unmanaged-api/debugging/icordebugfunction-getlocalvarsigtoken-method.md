---
title: Метод ICorDebugFunction::GetLocalVarSigToken
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetLocalVarSigToken
helpviewer_keywords:
- ICorDebugFunction::GetLocalVarSigToken method [.NET Framework debugging]
- GetLocalVarSigToken method [.NET Framework debugging]
ms.assetid: 31e53494-bcc9-4981-91a4-f7e0f02cad48
topic_type:
- apiref
ms.openlocfilehash: 3ad9697cf94a3dd89fbb00bdaa703632ddfcd6fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728138"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="f99b7-102">Метод ICorDebugFunction::GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="f99b7-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>

<span data-ttu-id="f99b7-103">Возвращает маркер метаданных для сигнатуры локальной переменной функции, представленной этим экземпляром ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="f99b7-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f99b7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f99b7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f99b7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f99b7-105">Parameters</span></span>  

 `pmdSig`  
 <span data-ttu-id="f99b7-106">заполняет Указатель на `mdSignature` маркер для сигнатуры локальной переменной этой функции или `mdSignatureNil` , если эта функция не имеет локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="f99b7-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f99b7-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f99b7-107">Requirements</span></span>  

 <span data-ttu-id="f99b7-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f99b7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f99b7-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f99b7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f99b7-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f99b7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f99b7-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f99b7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
