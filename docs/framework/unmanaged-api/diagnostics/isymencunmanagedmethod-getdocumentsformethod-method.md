---
title: Метод ISymENCUnmanagedMethod::GetDocumentsForMethod
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type:
- apiref
ms.openlocfilehash: 89be772ee3d8a6fc5acb74d5ebe6d3c691764f89
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441959"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="696f2-102">Метод ISymENCUnmanagedMethod::GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="696f2-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="696f2-103">Возвращает документы, в которых у этого метода есть строки.</span><span class="sxs-lookup"><span data-stu-id="696f2-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="696f2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="696f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="696f2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="696f2-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="696f2-106">окне Длина буфера, на который указывает `pcDocs` .</span><span class="sxs-lookup"><span data-stu-id="696f2-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="696f2-107">заполняет Указатель на объект `ULONG32` , который получает размер (в символах) буфера, необходимого для хранения документов.</span><span class="sxs-lookup"><span data-stu-id="696f2-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="696f2-108">окне Буфер, содержащий документы.</span><span class="sxs-lookup"><span data-stu-id="696f2-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="696f2-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="696f2-109">Return Value</span></span>  
 <span data-ttu-id="696f2-110">S_OK, если метод выполнен. в противном случае — код ошибки.</span><span class="sxs-lookup"><span data-stu-id="696f2-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="696f2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="696f2-111">Requirements</span></span>  
 <span data-ttu-id="696f2-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="696f2-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="696f2-113">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="696f2-113">See also</span></span>

- [<span data-ttu-id="696f2-114">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="696f2-114">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
