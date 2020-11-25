---
title: Метод ISymENCUnmanagedMethod::GetDocumentsForMethodCount
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethodCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount
helpviewer_keywords:
- GetDocumentsForMethodCount method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount method [.NET Framework debugging]
ms.assetid: cc1a823a-3ff3-4a33-b641-96edc93d2b17
topic_type:
- apiref
ms.openlocfilehash: 53897b6f964afb1f8ca95bc8f93c532e148ad129
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730517"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="3e8f5-102">Метод ISymENCUnmanagedMethod::GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="3e8f5-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>

<span data-ttu-id="3e8f5-103">Возвращает число документов, в которых у этого метода есть строки.</span><span class="sxs-lookup"><span data-stu-id="3e8f5-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e8f5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e8f5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e8f5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3e8f5-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="3e8f5-106">заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения документов.</span><span class="sxs-lookup"><span data-stu-id="3e8f5-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e8f5-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3e8f5-107">Return Value</span></span>  

 <span data-ttu-id="3e8f5-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="3e8f5-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e8f5-109">Требования</span><span class="sxs-lookup"><span data-stu-id="3e8f5-109">Requirements</span></span>  

 <span data-ttu-id="3e8f5-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="3e8f5-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e8f5-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3e8f5-111">See also</span></span>

- [<span data-ttu-id="3e8f5-112">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="3e8f5-112">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
