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
ms.openlocfilehash: 031e9d9434bc655ba8947a2bb6aba56a150e9002
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614465"
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="bb3d2-102">Метод ISymUnmanagedMethod::GetParameters</span><span class="sxs-lookup"><span data-stu-id="bb3d2-102">ISymUnmanagedMethod::GetParameters Method</span></span>
<span data-ttu-id="bb3d2-103">Возвращает параметры для этого метода.</span><span class="sxs-lookup"><span data-stu-id="bb3d2-103">Gets the parameters for this method.</span></span> <span data-ttu-id="bb3d2-104">Параметры возвращаются в том порядке, в котором они определены в сигнатуре метода.</span><span class="sxs-lookup"><span data-stu-id="bb3d2-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb3d2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb3d2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb3d2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb3d2-106">Parameters</span></span>  
 `cParams`  
 <span data-ttu-id="bb3d2-107">[in] Размер массива `params`.</span><span class="sxs-lookup"><span data-stu-id="bb3d2-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="bb3d2-108">окне Указатель на объект `ULONG32` , который получает размер буфера, который требуется для хранения параметров.</span><span class="sxs-lookup"><span data-stu-id="bb3d2-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="bb3d2-109">заполняет Указатель на буфер, который получает параметры.</span><span class="sxs-lookup"><span data-stu-id="bb3d2-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb3d2-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bb3d2-110">Return Value</span></span>  
 <span data-ttu-id="bb3d2-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="bb3d2-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb3d2-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bb3d2-112">Requirements</span></span>  
 <span data-ttu-id="bb3d2-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="bb3d2-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb3d2-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="bb3d2-114">See also</span></span>

- [<span data-ttu-id="bb3d2-115">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="bb3d2-115">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
