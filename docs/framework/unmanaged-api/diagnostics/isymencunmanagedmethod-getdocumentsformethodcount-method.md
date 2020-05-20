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
ms.openlocfilehash: d096101189d52401c407a4108c9c81e201d3f30d
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441946"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="dba80-102">Метод ISymENCUnmanagedMethod::GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="dba80-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>
<span data-ttu-id="dba80-103">Возвращает число документов, в которых у этого метода есть строки.</span><span class="sxs-lookup"><span data-stu-id="dba80-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dba80-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dba80-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dba80-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dba80-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="dba80-106">заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения документов.</span><span class="sxs-lookup"><span data-stu-id="dba80-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dba80-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dba80-107">Return Value</span></span>  
 <span data-ttu-id="dba80-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="dba80-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dba80-109">Требования</span><span class="sxs-lookup"><span data-stu-id="dba80-109">Requirements</span></span>  
 <span data-ttu-id="dba80-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="dba80-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dba80-111">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="dba80-111">See also</span></span>

- [<span data-ttu-id="dba80-112">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="dba80-112">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
