---
title: Метод ISymUnmanagedWriter::Close
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Close
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type:
- apiref
ms.openlocfilehash: 1d684c14f14fcc93040798ae4ee3b8bb1df5354d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733260"
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="23f2d-102">Метод ISymUnmanagedWriter::Close</span><span class="sxs-lookup"><span data-stu-id="23f2d-102">ISymUnmanagedWriter::Close Method</span></span>

<span data-ttu-id="23f2d-103">Закрывает модуль записи символов после фиксации символов в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="23f2d-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23f2d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23f2d-104">Syntax</span></span>  
  
```cpp  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="23f2d-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="23f2d-105">Return Value</span></span>  

 <span data-ttu-id="23f2d-106">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="23f2d-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23f2d-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="23f2d-107">Remarks</span></span>  

 <span data-ttu-id="23f2d-108">После этого вызова средство записи символов станет недействительным для последующих обновлений.</span><span class="sxs-lookup"><span data-stu-id="23f2d-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="23f2d-109">Чтобы закрыть средство записи символов без фиксации символов, следует использовать метод [ISymUnmanagedWriter:: Abort](isymunmanagedwriter-abort-method.md) .</span><span class="sxs-lookup"><span data-stu-id="23f2d-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23f2d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="23f2d-110">Requirements</span></span>  

 <span data-ttu-id="23f2d-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="23f2d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23f2d-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="23f2d-112">See also</span></span>

- [<span data-ttu-id="23f2d-113">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="23f2d-113">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
