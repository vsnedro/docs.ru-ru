---
title: Метод ISymUnmanagedWriter::Abort
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Abort
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type:
- apiref
ms.openlocfilehash: 2136eb32f147b8928e6ac90b99bbdf66804f244d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733273"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="cff80-102">Метод ISymUnmanagedWriter::Abort</span><span class="sxs-lookup"><span data-stu-id="cff80-102">ISymUnmanagedWriter::Abort Method</span></span>

<span data-ttu-id="cff80-103">Закрывает модуль записи символов без фиксации символов в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="cff80-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="cff80-104">После этого вызова средство записи символов станет недействительным для последующих обновлений.</span><span class="sxs-lookup"><span data-stu-id="cff80-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="cff80-105">Чтобы зафиксировать символы и закрыть средство записи символов, используйте вместо этого метод [ISymUnmanagedWriter:: Close](isymunmanagedwriter-close-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cff80-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cff80-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cff80-106">Syntax</span></span>  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="cff80-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cff80-107">Return Value</span></span>  

 <span data-ttu-id="cff80-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="cff80-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cff80-109">Требования</span><span class="sxs-lookup"><span data-stu-id="cff80-109">Requirements</span></span>  

 <span data-ttu-id="cff80-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="cff80-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cff80-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cff80-111">See also</span></span>

- [<span data-ttu-id="cff80-112">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="cff80-112">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
