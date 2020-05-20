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
ms.openlocfilehash: 09f39d3b6486e2ec3c04c5d1858a85ce56895527
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610162"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="7aa7f-102">Метод ISymUnmanagedWriter::Abort</span><span class="sxs-lookup"><span data-stu-id="7aa7f-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="7aa7f-103">Закрывает модуль записи символов без фиксации символов в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="7aa7f-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="7aa7f-104">После этого вызова средство записи символов станет недействительным для последующих обновлений.</span><span class="sxs-lookup"><span data-stu-id="7aa7f-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="7aa7f-105">Чтобы зафиксировать символы и закрыть средство записи символов, используйте вместо этого метод [ISymUnmanagedWriter:: Close](isymunmanagedwriter-close-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7aa7f-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aa7f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7aa7f-106">Syntax</span></span>  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7aa7f-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7aa7f-107">Return Value</span></span>  
 <span data-ttu-id="7aa7f-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="7aa7f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7aa7f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7aa7f-109">Requirements</span></span>  
 <span data-ttu-id="7aa7f-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="7aa7f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aa7f-111">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="7aa7f-111">See also</span></span>

- [<span data-ttu-id="7aa7f-112">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="7aa7f-112">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
