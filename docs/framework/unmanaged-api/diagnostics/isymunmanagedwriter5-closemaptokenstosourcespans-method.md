---
title: Метод ISymUnmanagedWriter5::CloseMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
ms.openlocfilehash: b57174f9f76b174927b8f1997beac3dd1482583a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725915"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="bdf06-102">Метод ISymUnmanagedWriter5::CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="bdf06-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>

<span data-ttu-id="bdf06-103">Закройте Специальный раздел настраиваемых данных, чтобы получить сведения о сопоставлении диапазона "токен-источник".</span><span class="sxs-lookup"><span data-stu-id="bdf06-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="bdf06-104">После закрытия не удается добавить дополнительные сведения о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="bdf06-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdf06-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdf06-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="bdf06-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bdf06-106">Return Value</span></span>  

 <span data-ttu-id="bdf06-107">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="bdf06-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdf06-108">Требования</span><span class="sxs-lookup"><span data-stu-id="bdf06-108">Requirements</span></span>  

 <span data-ttu-id="bdf06-109">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="bdf06-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdf06-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bdf06-110">See also</span></span>

- [<span data-ttu-id="bdf06-111">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="bdf06-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
