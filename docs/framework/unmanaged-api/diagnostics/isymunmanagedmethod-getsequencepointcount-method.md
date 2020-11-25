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
ms.openlocfilehash: 44472c7beff72d24853b7fb9865071a9b15ef0e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699434"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="ca59d-102">Метод ISymUnmanagedMethod::GetSequencePointCount</span><span class="sxs-lookup"><span data-stu-id="ca59d-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>

<span data-ttu-id="ca59d-103">Возвращает число точек следования в этом методе.</span><span class="sxs-lookup"><span data-stu-id="ca59d-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca59d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca59d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca59d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ca59d-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="ca59d-106">заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения точек следования.</span><span class="sxs-lookup"><span data-stu-id="ca59d-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca59d-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ca59d-107">Return Value</span></span>  

 <span data-ttu-id="ca59d-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="ca59d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca59d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ca59d-109">Requirements</span></span>  

 <span data-ttu-id="ca59d-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="ca59d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca59d-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ca59d-111">See also</span></span>

- [<span data-ttu-id="ca59d-112">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="ca59d-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
