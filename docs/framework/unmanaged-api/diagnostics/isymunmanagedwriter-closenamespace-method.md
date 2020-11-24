---
title: Метод ISymUnmanagedWriter::CloseNamespace
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::CloseNamespace method [.NET Framework debugging]
- CloseNamespace method [.NET Framework debugging]
ms.assetid: 7f74d9c5-1377-4958-b842-6306d611cbd5
topic_type:
- apiref
ms.openlocfilehash: 13a433157e0c92653edf234f1f1f885270196ffd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686414"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="5cfac-102">Метод ISymUnmanagedWriter::CloseNamespace</span><span class="sxs-lookup"><span data-stu-id="5cfac-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>

<span data-ttu-id="5cfac-103">Закрывает Последнее открытое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="5cfac-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cfac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cfac-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5cfac-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5cfac-105">Return Value</span></span>  

 <span data-ttu-id="5cfac-106">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="5cfac-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cfac-107">Требования</span><span class="sxs-lookup"><span data-stu-id="5cfac-107">Requirements</span></span>  

 <span data-ttu-id="5cfac-108">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="5cfac-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cfac-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5cfac-109">See also</span></span>

- [<span data-ttu-id="5cfac-110">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="5cfac-110">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="5cfac-111">Метод OpenNamespace</span><span class="sxs-lookup"><span data-stu-id="5cfac-111">OpenNamespace Method</span></span>](isymunmanagedwriter-opennamespace-method.md)
