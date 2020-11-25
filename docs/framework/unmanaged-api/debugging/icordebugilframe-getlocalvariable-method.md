---
title: Метод ICorDebugILFrame::GetLocalVariable
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetLocalVariable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type:
- apiref
ms.openlocfilehash: 54ecce830b928ded115233eb99932cc15a471033
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703139"
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="89775-102">Метод ICorDebugILFrame::GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="89775-102">ICorDebugILFrame::GetLocalVariable Method</span></span>

<span data-ttu-id="89775-103">Возвращает значение указанной локальной переменной в кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="89775-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89775-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89775-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89775-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="89775-105">Parameters</span></span>  

 `dwIndex`  
 <span data-ttu-id="89775-106">окне Индекс локальной переменной в этом кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="89775-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="89775-107">[из] Указатель на адрес объекта ICorDebugValue, представляющего извлеченное значение.</span><span class="sxs-lookup"><span data-stu-id="89775-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89775-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="89775-108">Remarks</span></span>  

 <span data-ttu-id="89775-109">`GetLocalVariable`Метод можно использовать либо в кадре стека MSIL, либо в кадре JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="89775-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89775-110">Требования</span><span class="sxs-lookup"><span data-stu-id="89775-110">Requirements</span></span>  

 <span data-ttu-id="89775-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89775-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89775-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89775-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89775-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89775-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89775-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89775-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
