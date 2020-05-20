---
title: Метод ISymUnmanagedMethod::GetSequencePointCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePointCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePointCount
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePointCount method [.NET Framework debugging]
- GetSequencePointCount method [.NET Framework debugging]
ms.assetid: 836133e8-6108-4b9b-b0a9-bce4e08dccda
topic_type:
- apiref
ms.openlocfilehash: a44f81deb2d57b49f1fd0650fa52c06383210352
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614439"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="474d6-102">Метод ISymUnmanagedMethod::GetSequencePointCount</span><span class="sxs-lookup"><span data-stu-id="474d6-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="474d6-103">Возвращает число точек следования в этом методе.</span><span class="sxs-lookup"><span data-stu-id="474d6-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="474d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="474d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="474d6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="474d6-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="474d6-106">заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения точек следования.</span><span class="sxs-lookup"><span data-stu-id="474d6-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="474d6-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="474d6-107">Return Value</span></span>  
 <span data-ttu-id="474d6-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="474d6-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="474d6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="474d6-109">Requirements</span></span>  
 <span data-ttu-id="474d6-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="474d6-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="474d6-111">См. также статью</span><span class="sxs-lookup"><span data-stu-id="474d6-111">See also</span></span>

- [<span data-ttu-id="474d6-112">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="474d6-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
