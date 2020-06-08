---
title: Интерфейс ISymUnmanagedAsyncMethod
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: 448ed719331469dce8f15500f14d5c1b0707ecf7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504456"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="68199-102">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="68199-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="68199-103">Этот интерфейс является дополнением к [интерфейсу метод isymunmanagedasyncmethodpropertieswriter](isymunmanagedasyncmethodpropertieswriter-interface.md)для чтения.</span><span class="sxs-lookup"><span data-stu-id="68199-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68199-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68199-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="68199-105">Методы</span><span class="sxs-lookup"><span data-stu-id="68199-105">Methods</span></span>  
 <span data-ttu-id="68199-106">Этот интерфейс содержит следующие методы:</span><span class="sxs-lookup"><span data-stu-id="68199-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="68199-107">Метод</span><span class="sxs-lookup"><span data-stu-id="68199-107">Method</span></span>|<span data-ttu-id="68199-108">Описание</span><span class="sxs-lookup"><span data-stu-id="68199-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="68199-109">Метод GetAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="68199-109">GetAsyncStepInfo Method</span></span>](isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="68199-110">См. раздел [метод дефинеасинкстепинфо](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="68199-110">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="68199-111">Метод GetAsyncStepInfoCount</span><span class="sxs-lookup"><span data-stu-id="68199-111">GetAsyncStepInfoCount Method</span></span>](isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="68199-112">См. раздел [метод дефинеасинкстепинфо](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="68199-112">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="68199-113">Метод GetCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="68199-113">GetCatchHandlerILOffset Method</span></span>](isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="68199-114">См. раздел [метод DefineCatchHandlerILOffset](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="68199-114">See [DefineCatchHandlerILOffset Method](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="68199-115">Метод GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="68199-115">GetKickoffMethod Method</span></span>](isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="68199-116">См. раздел [метод DefineKickoffMethod](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="68199-116">See [DefineKickoffMethod Method](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="68199-117">Метод HasCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="68199-117">HasCatchHandlerILOffset Method</span></span>](isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="68199-118">См. раздел [метод DefineCatchHandlerILOffset](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="68199-118">See [DefineCatchHandlerILOffset Method](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="68199-119">Метод IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="68199-119">IsAsyncMethod Method</span></span>](isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="68199-120">Проверяет, имеет ли метод асинхронную информацию.</span><span class="sxs-lookup"><span data-stu-id="68199-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="68199-121">Если этот метод возвращает значение `FALSE` , то он недопустим для вызова любых других методов в этом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="68199-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="68199-122">`E_UNEXPECTED`В этом случае они будут возвращаться.</span><span class="sxs-lookup"><span data-stu-id="68199-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="68199-123">Требования</span><span class="sxs-lookup"><span data-stu-id="68199-123">Requirements</span></span>  
 <span data-ttu-id="68199-124">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="68199-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68199-125">См. также</span><span class="sxs-lookup"><span data-stu-id="68199-125">See also</span></span>

- [<span data-ttu-id="68199-126">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="68199-126">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
