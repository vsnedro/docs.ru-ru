---
title: Метод ISymUnmanagedSymbolSearchInfo::GetHRESULT
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetHRESULT
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT method [.NET Framework debugging]
- GetHRESULT method [.NET Framework debugging]
ms.assetid: 6999dc3d-65d7-4bf6-bb0a-6efc0fc72588
topic_type:
- apiref
ms.openlocfilehash: a931c15b1c4a9f099d11c43edd324cfcc2793090
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722275"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="ae904-102">Метод ISymUnmanagedSymbolSearchInfo::GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="ae904-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>

<span data-ttu-id="ae904-103">Возвращает значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="ae904-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae904-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ae904-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae904-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ae904-105">Parameters</span></span>  

 `phr`  
 <span data-ttu-id="ae904-106">заполняет Указатель на значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="ae904-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae904-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ae904-107">Return Value</span></span>  

 <span data-ttu-id="ae904-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="ae904-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae904-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ae904-109">Requirements</span></span>  

 <span data-ttu-id="ae904-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="ae904-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae904-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ae904-111">See also</span></span>

- [<span data-ttu-id="ae904-112">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="ae904-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
