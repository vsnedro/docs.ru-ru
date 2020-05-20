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
ms.openlocfilehash: 68a0f9ec8793d465a6fa3b1cb6936eddd7be4c8f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615414"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a><span data-ttu-id="daff2-102">Метод ISymUnmanagedReader2::GetMethodsInDocument</span><span class="sxs-lookup"><span data-stu-id="daff2-102">ISymUnmanagedReader2::GetMethodsInDocument Method</span></span>
<span data-ttu-id="daff2-103">Возвращает каждый метод, имеющий сведения о строке в указанном документе.</span><span class="sxs-lookup"><span data-stu-id="daff2-103">Gets every method that has line information in the provided document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daff2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="daff2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="daff2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="daff2-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="daff2-106">окне Указатель на документ.</span><span class="sxs-lookup"><span data-stu-id="daff2-106">[in] A pointer to the document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="daff2-107">окне Значение типа `ULONG32` , указывающее размер `pRetVal` массива.</span><span class="sxs-lookup"><span data-stu-id="daff2-107">[in] A `ULONG32` that indicates the size of the  `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="daff2-108">заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения методов.</span><span class="sxs-lookup"><span data-stu-id="daff2-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the methods.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="daff2-109">заполняет Указатель на буфер, который получает методы.</span><span class="sxs-lookup"><span data-stu-id="daff2-109">[out] A pointer to the buffer that receives the methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="daff2-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="daff2-110">Return Value</span></span>  
 <span data-ttu-id="daff2-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="daff2-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daff2-112">Требования</span><span class="sxs-lookup"><span data-stu-id="daff2-112">Requirements</span></span>  
 <span data-ttu-id="daff2-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="daff2-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daff2-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="daff2-114">See also</span></span>

- [<span data-ttu-id="daff2-115">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="daff2-115">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
