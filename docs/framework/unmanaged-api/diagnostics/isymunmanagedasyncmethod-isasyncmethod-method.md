---
title: Метод ISymUnmanagedAsyncMethod::IsAsyncMethod
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: af02aba1a0d390c103e8c6108f90b93fe2a98ff3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707156"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="b5b69-102">Метод ISymUnmanagedAsyncMethod::IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="b5b69-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>

<span data-ttu-id="b5b69-103">Проверяет, имеет ли метод асинхронную информацию.</span><span class="sxs-lookup"><span data-stu-id="b5b69-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="b5b69-104">Если этот метод возвращает значение `FALSE` , то он недопустим для вызова любых других методов в этом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="b5b69-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="b5b69-105">`E_UNEXPECTED`В этом случае они будут возвращаться.</span><span class="sxs-lookup"><span data-stu-id="b5b69-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5b69-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5b69-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5b69-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="b5b69-107">Parameters</span></span>  
  
|<span data-ttu-id="b5b69-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="b5b69-108">Parameter</span></span>|<span data-ttu-id="b5b69-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b5b69-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="b5b69-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b5b69-110">Return Value</span></span>  

 <span data-ttu-id="b5b69-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="b5b69-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5b69-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b5b69-112">Requirements</span></span>  

 <span data-ttu-id="b5b69-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="b5b69-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5b69-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b5b69-114">See also</span></span>

- [<span data-ttu-id="b5b69-115">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="b5b69-115">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
