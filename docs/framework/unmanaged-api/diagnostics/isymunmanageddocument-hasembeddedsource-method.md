---
title: Метод ISymUnmanagedDocument::HasEmbeddedSource
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.HasEmbeddedSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type:
- apiref
ms.openlocfilehash: 09bc0f87cd35f12a15566fb525c2ce42990ac69b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688202"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="6c8b9-102">Метод ISymUnmanagedDocument::HasEmbeddedSource</span><span class="sxs-lookup"><span data-stu-id="6c8b9-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>

<span data-ttu-id="6c8b9-103">Возвращает `true` , если документ имеет исходный код, внедренный в отладочные символы; в противном случае возвращает `false` .</span><span class="sxs-lookup"><span data-stu-id="6c8b9-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c8b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c8b9-104">Syntax</span></span>  
  
```cpp  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c8b9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6c8b9-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="6c8b9-106">заполняет Указатель на переменную, которая указывает, имеет ли документ исходный код, внедренный в отладочные символы.</span><span class="sxs-lookup"><span data-stu-id="6c8b9-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c8b9-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6c8b9-107">Return Value</span></span>  

 <span data-ttu-id="6c8b9-108">S_OK, если метод выполнен.</span><span class="sxs-lookup"><span data-stu-id="6c8b9-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c8b9-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6c8b9-109">See also</span></span>

- [<span data-ttu-id="6c8b9-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="6c8b9-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
