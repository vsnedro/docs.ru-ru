---
title: Метод ISymUnmanagedWriter5::MapTokenToSourceSpan
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
ms.openlocfilehash: e4b09e6d89b3ba8ba3bf7e149d31a14a74b945b5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723939"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="5aec5-102">Метод ISymUnmanagedWriter5::MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="5aec5-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>

<span data-ttu-id="5aec5-103">Сопоставляет заданный токен метаданных с заданным диапазоном исходной строки в указанном исходном файле.</span><span class="sxs-lookup"><span data-stu-id="5aec5-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="5aec5-104">Должен вызываться между вызовами [метода OpenMapTokensToSourceSpans](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) и [метода CloseMapTokensToSourceSpans](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="5aec5-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5aec5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5aec5-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5aec5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5aec5-106">Parameters</span></span>  
  
|<span data-ttu-id="5aec5-107">Параметр</span><span class="sxs-lookup"><span data-stu-id="5aec5-107">Parameter</span></span>|<span data-ttu-id="5aec5-108">Описание</span><span class="sxs-lookup"><span data-stu-id="5aec5-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="5aec5-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5aec5-109">Return Value</span></span>  

 <span data-ttu-id="5aec5-110">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="5aec5-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5aec5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5aec5-111">Requirements</span></span>  

 <span data-ttu-id="5aec5-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="5aec5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aec5-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5aec5-113">See also</span></span>

- [<span data-ttu-id="5aec5-114">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="5aec5-114">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
