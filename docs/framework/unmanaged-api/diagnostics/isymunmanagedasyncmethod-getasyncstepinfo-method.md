---
title: Метод ISymUnmanagedAsyncMethod::GetAsyncStepInfo
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
ms.openlocfilehash: f9392dae4119e59b4eb0fdb87e2b334b32b77109
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707260"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="04f5b-102">Метод ISymUnmanagedAsyncMethod::GetAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="04f5b-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>

<span data-ttu-id="04f5b-103">См. раздел [метод дефинеасинкстепинфо](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="04f5b-103">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04f5b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04f5b-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04f5b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="04f5b-105">Parameters</span></span>  
  
|<span data-ttu-id="04f5b-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="04f5b-106">Parameter</span></span>|<span data-ttu-id="04f5b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="04f5b-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="04f5b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="04f5b-108">Return Value</span></span>  

 <span data-ttu-id="04f5b-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="04f5b-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04f5b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="04f5b-110">Requirements</span></span>  

 <span data-ttu-id="04f5b-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="04f5b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f5b-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="04f5b-112">See also</span></span>

- [<span data-ttu-id="04f5b-113">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="04f5b-113">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
