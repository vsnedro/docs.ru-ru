---
title: Метод ISymUnmanagedWriter5::CloseMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
ms.openlocfilehash: 053727604c795bf43a9b1658d5841fe85f53090a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614634"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="3b0c9-102">Метод ISymUnmanagedWriter5::CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="3b0c9-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="3b0c9-103">Закройте Специальный раздел настраиваемых данных, чтобы получить сведения о сопоставлении диапазона "токен-источник".</span><span class="sxs-lookup"><span data-stu-id="3b0c9-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="3b0c9-104">После закрытия не удается добавить дополнительные сведения о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="3b0c9-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b0c9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b0c9-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3b0c9-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3b0c9-106">Return Value</span></span>  
 <span data-ttu-id="3b0c9-107">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="3b0c9-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b0c9-108">Требования</span><span class="sxs-lookup"><span data-stu-id="3b0c9-108">Requirements</span></span>  
 <span data-ttu-id="3b0c9-109">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="3b0c9-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b0c9-110">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="3b0c9-110">See also</span></span>

- [<span data-ttu-id="3b0c9-111">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="3b0c9-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
