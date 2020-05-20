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
ms.openlocfilehash: 5bd94cb851d4bb044d4ce03b97d6342a2c9652e4
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441322"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="bf2e0-102">Метод ISymUnmanagedDispose::Destroy</span><span class="sxs-lookup"><span data-stu-id="bf2e0-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="bf2e0-103">Заставляет базовый объект освобождать все внутренние ссылки и возвращать ошибку при любом последующем вызове метода.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf2e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf2e0-104">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="bf2e0-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bf2e0-105">Return Value</span></span>  
 <span data-ttu-id="bf2e0-106">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf2e0-107">Требования</span><span class="sxs-lookup"><span data-stu-id="bf2e0-107">Requirements</span></span>  
 <span data-ttu-id="bf2e0-108">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="bf2e0-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf2e0-109">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="bf2e0-109">See also</span></span>

- [<span data-ttu-id="bf2e0-110">Интерфейс ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="bf2e0-110">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)
