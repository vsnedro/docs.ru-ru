---
title: Метод ISymUnmanagedReader2::GetMethodsInDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodsInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument
helpviewer_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument method [.NET Framework debugging]
- GetMethodsInDocument method [.NET Framework debugging]
ms.assetid: c7ae84d6-81e8-4cb7-a1f9-d48b6cde5d79
topic_type:
- apiref
ms.openlocfilehash: 2e7eb183200c6e6de8ee18b58aab457c7e7bf2eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675754"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a><span data-ttu-id="49d0b-102">Метод ISymUnmanagedReader2::GetMethodsInDocument</span><span class="sxs-lookup"><span data-stu-id="49d0b-102">ISymUnmanagedReader2::GetMethodsInDocument Method</span></span>

<span data-ttu-id="49d0b-103">Возвращает каждый метод, имеющий сведения о строке в указанном документе.</span><span class="sxs-lookup"><span data-stu-id="49d0b-103">Gets every method that has line information in the provided document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49d0b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49d0b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49d0b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="49d0b-105">Parameters</span></span>  

 `document`  
 <span data-ttu-id="49d0b-106">окне Указатель на документ.</span><span class="sxs-lookup"><span data-stu-id="49d0b-106">[in] A pointer to the document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="49d0b-107">окне Значение типа `ULONG32` , указывающее размер  `pRetVal` массива.</span><span class="sxs-lookup"><span data-stu-id="49d0b-107">[in] A `ULONG32` that indicates the size of the  `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="49d0b-108">заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения методов.</span><span class="sxs-lookup"><span data-stu-id="49d0b-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the methods.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="49d0b-109">заполняет Указатель на буфер, который получает методы.</span><span class="sxs-lookup"><span data-stu-id="49d0b-109">[out] A pointer to the buffer that receives the methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49d0b-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="49d0b-110">Return Value</span></span>  

 <span data-ttu-id="49d0b-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="49d0b-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49d0b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="49d0b-112">Requirements</span></span>  

 <span data-ttu-id="49d0b-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="49d0b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49d0b-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="49d0b-114">See also</span></span>

- [<span data-ttu-id="49d0b-115">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="49d0b-115">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
