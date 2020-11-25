---
title: Метод ISymUnmanagedDispose::Destroy
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose.Destroy
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose::Destroy
helpviewer_keywords:
- ISymUnmanagedDispose::Destroy method [.NET Framework debugging]
- Destroy method [.NET Framework debugging]
ms.assetid: a854ab9f-d2ba-470e-867f-808c1e7bd07a
topic_type:
- apiref
ms.openlocfilehash: 6a31026f5b1669c0c29762048dc2c5c1c7bbb6a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732831"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="cae34-102">Метод ISymUnmanagedDispose::Destroy</span><span class="sxs-lookup"><span data-stu-id="cae34-102">ISymUnmanagedDispose::Destroy Method</span></span>

<span data-ttu-id="cae34-103">Заставляет базовый объект освобождать все внутренние ссылки и возвращать ошибку при любом последующем вызове метода.</span><span class="sxs-lookup"><span data-stu-id="cae34-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cae34-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cae34-104">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="cae34-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cae34-105">Return Value</span></span>  

 <span data-ttu-id="cae34-106">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="cae34-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cae34-107">Требования</span><span class="sxs-lookup"><span data-stu-id="cae34-107">Requirements</span></span>  

 <span data-ttu-id="cae34-108">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="cae34-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cae34-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cae34-109">See also</span></span>

- [<span data-ttu-id="cae34-110">Интерфейс ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="cae34-110">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)
