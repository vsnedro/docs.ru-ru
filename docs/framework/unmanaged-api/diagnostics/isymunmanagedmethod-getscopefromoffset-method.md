---
title: Метод ISymUnmanagedMethod::GetScopeFromOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
ms.openlocfilehash: 4eefd019280f501a6ce194e5ce84388e32cc66e1
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615167"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="46a0f-102">Метод ISymUnmanagedMethod::GetScopeFromOffset</span><span class="sxs-lookup"><span data-stu-id="46a0f-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>
<span data-ttu-id="46a0f-103">Возвращает наиболее окружающую лексическую область внутри этого метода, которая заключает заданное смещение.</span><span class="sxs-lookup"><span data-stu-id="46a0f-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="46a0f-104">Это можно использовать для запуска поиска локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="46a0f-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46a0f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46a0f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46a0f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="46a0f-106">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="46a0f-107">окне Значение типа `ULONG` , содержащее смещение.</span><span class="sxs-lookup"><span data-stu-id="46a0f-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="46a0f-108">заполняет Указатель, которому присваивается возвращаемый интерфейс [исимунманажедскопе](isymunmanagedscope-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="46a0f-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46a0f-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="46a0f-109">Return Value</span></span>  
 <span data-ttu-id="46a0f-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="46a0f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46a0f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="46a0f-111">Requirements</span></span>  
 <span data-ttu-id="46a0f-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="46a0f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46a0f-113">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="46a0f-113">See also</span></span>

- [<span data-ttu-id="46a0f-114">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="46a0f-114">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
