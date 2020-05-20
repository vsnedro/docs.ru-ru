---
title: Метод ISymUnmanagedReader::GetDocuments
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocuments
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocuments
helpviewer_keywords:
- GetDocuments method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocuments method [.NET Framework debugging]
ms.assetid: e3b73a3f-d089-4101-a9a9-5e0765d05b61
topic_type:
- apiref
ms.openlocfilehash: b8a3a74888a3caae03da6f88a003bd277939ae59
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615050"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="c1da4-102">Метод ISymUnmanagedReader::GetDocuments</span><span class="sxs-lookup"><span data-stu-id="c1da4-102">ISymUnmanagedReader::GetDocuments Method</span></span>
<span data-ttu-id="c1da4-103">Возвращает массив всех документов, определенных в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="c1da4-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1da4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1da4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1da4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c1da4-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="c1da4-106">[in] Размер массива `pDocs`.</span><span class="sxs-lookup"><span data-stu-id="c1da4-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="c1da4-107">заполняет Указатель на переменную, которая получает длину массива.</span><span class="sxs-lookup"><span data-stu-id="c1da4-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="c1da4-108">заполняет Указатель на переменную, которая получает массив документов.</span><span class="sxs-lookup"><span data-stu-id="c1da4-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1da4-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c1da4-109">Return Value</span></span>  
 <span data-ttu-id="c1da4-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="c1da4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1da4-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c1da4-111">Requirements</span></span>  
 <span data-ttu-id="c1da4-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="c1da4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1da4-113">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="c1da4-113">See also</span></span>

- [<span data-ttu-id="c1da4-114">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="c1da4-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
