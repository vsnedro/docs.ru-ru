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
ms.openlocfilehash: d654f6d57bd784063fc7f87dd9767bdc27ad2776
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615583"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="70d11-102">Метод ISymUnmanagedDocument::HasEmbeddedSource</span><span class="sxs-lookup"><span data-stu-id="70d11-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="70d11-103">Возвращает `true` , если документ имеет исходный код, внедренный в отладочные символы; в противном случае возвращает `false` .</span><span class="sxs-lookup"><span data-stu-id="70d11-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70d11-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70d11-104">Syntax</span></span>  
  
```cpp  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70d11-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="70d11-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="70d11-106">заполняет Указатель на переменную, которая указывает, имеет ли документ исходный код, внедренный в отладочные символы.</span><span class="sxs-lookup"><span data-stu-id="70d11-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70d11-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="70d11-107">Return Value</span></span>  
 <span data-ttu-id="70d11-108">S_OK, если метод выполнен.</span><span class="sxs-lookup"><span data-stu-id="70d11-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70d11-109">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="70d11-109">See also</span></span>

- [<span data-ttu-id="70d11-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="70d11-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
