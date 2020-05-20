---
title: Метод ISymUnmanagedAsyncMethod::GetKickoffMethod
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
ms.openlocfilehash: 879b9eac7cb6df06ffe4f994b505ea9cb2396d7f
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441842"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="ba25d-102">Метод ISymUnmanagedAsyncMethod::GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="ba25d-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="ba25d-103">См. раздел [метод DefineKickoffMethod](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="ba25d-103">See [DefineKickoffMethod Method](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba25d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba25d-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba25d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ba25d-105">Parameters</span></span>  
  
|<span data-ttu-id="ba25d-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="ba25d-106">Parameter</span></span>|<span data-ttu-id="ba25d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ba25d-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="ba25d-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ba25d-108">Return Value</span></span>  
 <span data-ttu-id="ba25d-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="ba25d-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba25d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ba25d-110">Requirements</span></span>  
 <span data-ttu-id="ba25d-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="ba25d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba25d-112">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="ba25d-112">See also</span></span>

- [<span data-ttu-id="ba25d-113">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="ba25d-113">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
