---
title: Метод ISymUnmanagedAsyncMethod::IsAsyncMethod
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 91b4c2688dadf12fa4a835a662622267d7831cf8
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441803"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="f44ce-102">Метод ISymUnmanagedAsyncMethod::IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="f44ce-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="f44ce-103">Проверяет, имеет ли метод асинхронную информацию.</span><span class="sxs-lookup"><span data-stu-id="f44ce-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="f44ce-104">Если этот метод возвращает значение `FALSE` , то он недопустим для вызова любых других методов в этом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="f44ce-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="f44ce-105">`E_UNEXPECTED`В этом случае они будут возвращаться.</span><span class="sxs-lookup"><span data-stu-id="f44ce-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f44ce-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f44ce-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f44ce-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="f44ce-107">Parameters</span></span>  
  
|<span data-ttu-id="f44ce-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="f44ce-108">Parameter</span></span>|<span data-ttu-id="f44ce-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f44ce-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="f44ce-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f44ce-110">Return Value</span></span>  
 <span data-ttu-id="f44ce-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="f44ce-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f44ce-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f44ce-112">Requirements</span></span>  
 <span data-ttu-id="f44ce-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="f44ce-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f44ce-114">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="f44ce-114">See also</span></span>

- [<span data-ttu-id="f44ce-115">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="f44ce-115">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
