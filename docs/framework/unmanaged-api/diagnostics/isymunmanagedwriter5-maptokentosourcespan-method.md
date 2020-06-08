---
title: Метод ISymUnmanagedWriter5::MapTokenToSourceSpan
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
ms.openlocfilehash: 0f00dd34ffbdd58a46260132d8d7ace74ec2f294
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501681"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="09125-102">Метод ISymUnmanagedWriter5::MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="09125-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="09125-103">Сопоставляет заданный токен метаданных с заданным диапазоном исходной строки в указанном исходном файле.</span><span class="sxs-lookup"><span data-stu-id="09125-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="09125-104">Должен вызываться между вызовами [метода OpenMapTokensToSourceSpans](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) и [метода CloseMapTokensToSourceSpans](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="09125-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09125-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09125-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09125-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="09125-106">Parameters</span></span>  
  
|<span data-ttu-id="09125-107">Параметр</span><span class="sxs-lookup"><span data-stu-id="09125-107">Parameter</span></span>|<span data-ttu-id="09125-108">Описание</span><span class="sxs-lookup"><span data-stu-id="09125-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="09125-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="09125-109">Return Value</span></span>  
 <span data-ttu-id="09125-110">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="09125-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09125-111">Требования</span><span class="sxs-lookup"><span data-stu-id="09125-111">Requirements</span></span>  
 <span data-ttu-id="09125-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="09125-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09125-113">См. также</span><span class="sxs-lookup"><span data-stu-id="09125-113">See also</span></span>

- [<span data-ttu-id="09125-114">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="09125-114">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
