---
title: Метод ISymUnmanagedDocument::GetLanguage
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguage
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguage
helpviewer_keywords:
- ISymUnmanagedDocument::GetLanguage method [.NET Framework debugging]
- GetLanguage method [.NET Framework debugging]
ms.assetid: c6639418-e9f2-4a99-8ce2-ec9876e0bc79
topic_type:
- apiref
ms.openlocfilehash: 084f3ae12d906f5e80fdb86e65b09d2371fd246b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614595"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="d66c6-102">Метод ISymUnmanagedDocument::GetLanguage</span><span class="sxs-lookup"><span data-stu-id="d66c6-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="d66c6-103">Возвращает идентификатор языка этого документа.</span><span class="sxs-lookup"><span data-stu-id="d66c6-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d66c6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d66c6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d66c6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d66c6-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="d66c6-106">заполняет Указатель на переменную, которая получает идентификатор языка.</span><span class="sxs-lookup"><span data-stu-id="d66c6-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d66c6-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d66c6-107">Return Value</span></span>  
 <span data-ttu-id="d66c6-108">S_OK, если метод выполнен.</span><span class="sxs-lookup"><span data-stu-id="d66c6-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d66c6-109">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="d66c6-109">See also</span></span>

- [<span data-ttu-id="d66c6-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="d66c6-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
