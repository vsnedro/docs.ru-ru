---
title: Метод ISymUnmanagedBinder::GetReaderFromStream
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderFromStream
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type:
- apiref
ms.openlocfilehash: 2d927b02b7deebecb53a2218e2ec0275a07307b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706961"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="bf47d-102">Метод ISymUnmanagedBinder::GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="bf47d-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>

<span data-ttu-id="bf47d-103">При наличии интерфейса метаданных и потока, содержащего хранилище символов, возвращает правильную структуру [ISymUnmanagedReader](isymunmanagedreader-interface.md) , которая будет считывать отладочные символы из заданного хранилища символов.</span><span class="sxs-lookup"><span data-stu-id="bf47d-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf47d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf47d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf47d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf47d-105">Parameters</span></span>  

 `importer`  
 <span data-ttu-id="bf47d-106">окне Указатель на интерфейс импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="bf47d-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="bf47d-107">окне Указатель на поток, содержащий хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="bf47d-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="bf47d-108">заполняет Указатель, которому присваивается возвращаемый интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="bf47d-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf47d-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bf47d-109">Return Value</span></span>  

 <span data-ttu-id="bf47d-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="bf47d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf47d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="bf47d-111">Requirements</span></span>  

 <span data-ttu-id="bf47d-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="bf47d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf47d-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bf47d-113">See also</span></span>

- [<span data-ttu-id="bf47d-114">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="bf47d-114">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
