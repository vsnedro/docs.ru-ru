---
title: Метод ISymUnmanagedMethod::GetParameters
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetParameters
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetParameters
helpviewer_keywords:
- ISymUnmanagedMethod::GetParameters method [.NET Framework debugging]
- GetParameters method [.NET Framework debugging]
ms.assetid: 3a8074f1-facc-4a3f-bb9b-d6574fc2fc74
topic_type:
- apiref
ms.openlocfilehash: c66fd810ae4976bc0b5e04572b899465cebe4bbb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699512"
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="7ec63-102">Метод ISymUnmanagedMethod::GetParameters</span><span class="sxs-lookup"><span data-stu-id="7ec63-102">ISymUnmanagedMethod::GetParameters Method</span></span>

<span data-ttu-id="7ec63-103">Возвращает параметры для этого метода.</span><span class="sxs-lookup"><span data-stu-id="7ec63-103">Gets the parameters for this method.</span></span> <span data-ttu-id="7ec63-104">Параметры возвращаются в том порядке, в котором они определены в сигнатуре метода.</span><span class="sxs-lookup"><span data-stu-id="7ec63-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ec63-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ec63-105">Syntax</span></span>  
  
```cpp  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ec63-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7ec63-106">Parameters</span></span>  

 `cParams`  
 <span data-ttu-id="7ec63-107">[in] Размер массива `params`.</span><span class="sxs-lookup"><span data-stu-id="7ec63-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="7ec63-108">окне Указатель на объект `ULONG32` , который получает размер буфера, который требуется для хранения параметров.</span><span class="sxs-lookup"><span data-stu-id="7ec63-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="7ec63-109">заполняет Указатель на буфер, который получает параметры.</span><span class="sxs-lookup"><span data-stu-id="7ec63-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ec63-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7ec63-110">Return Value</span></span>  

 <span data-ttu-id="7ec63-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="7ec63-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ec63-112">Требования</span><span class="sxs-lookup"><span data-stu-id="7ec63-112">Requirements</span></span>  

 <span data-ttu-id="7ec63-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="7ec63-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ec63-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7ec63-114">See also</span></span>

- [<span data-ttu-id="7ec63-115">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="7ec63-115">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
