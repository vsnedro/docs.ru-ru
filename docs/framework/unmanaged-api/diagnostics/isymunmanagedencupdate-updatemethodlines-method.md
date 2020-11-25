---
title: Метод ISymUnmanagedENCUpdate::UpdateMethodLines
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateMethodLines
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type:
- apiref
ms.openlocfilehash: 99499b8717f219616b6b368e6393b4b7ca0a79d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699590"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="5be8f-102">Метод ISymUnmanagedENCUpdate::UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="5be8f-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>

<span data-ttu-id="5be8f-103">Позволяет обновлять сведения о строке для метода, который не был перекомпилирован, но строки были перемещены независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="5be8f-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="5be8f-104">Допускается использование разности для каждой инструкции.</span><span class="sxs-lookup"><span data-stu-id="5be8f-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5be8f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5be8f-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5be8f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5be8f-106">Parameters</span></span>  

 `mdMethodToken`  
 <span data-ttu-id="5be8f-107">окне Метаданные токена метода.</span><span class="sxs-lookup"><span data-stu-id="5be8f-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="5be8f-108">окне Массив `INT32` значений, указывающий разность для каждой точки следования в методе.</span><span class="sxs-lookup"><span data-stu-id="5be8f-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="5be8f-109">окне Значение типа, `ULONG` содержащее размер `pDeltas` параметра.</span><span class="sxs-lookup"><span data-stu-id="5be8f-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5be8f-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5be8f-110">Return Value</span></span>  

 <span data-ttu-id="5be8f-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="5be8f-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5be8f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="5be8f-112">Requirements</span></span>  

 <span data-ttu-id="5be8f-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="5be8f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5be8f-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5be8f-114">See also</span></span>

- [<span data-ttu-id="5be8f-115">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="5be8f-115">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
