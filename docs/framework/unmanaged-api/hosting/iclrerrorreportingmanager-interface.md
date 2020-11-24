---
title: Интерфейс ICLRErrorReportingManager
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
ms.openlocfilehash: d3816c8a3b6204b053505aa888eb28d696f8990b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677852"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="895a7-102">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="895a7-102">ICLRErrorReportingManager Interface</span></span>

<span data-ttu-id="895a7-103">Предоставляет методы, позволяющие основному приложению настраивать пользовательские дампы стека для отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="895a7-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="895a7-104">Методы</span><span class="sxs-lookup"><span data-stu-id="895a7-104">Methods</span></span>  
  
|<span data-ttu-id="895a7-105">Метод</span><span class="sxs-lookup"><span data-stu-id="895a7-105">Method</span></span>|<span data-ttu-id="895a7-106">Описание</span><span class="sxs-lookup"><span data-stu-id="895a7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="895a7-107">Метод BeginCustomDump</span><span class="sxs-lookup"><span data-stu-id="895a7-107">BeginCustomDump Method</span></span>](iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="895a7-108">Задает конфигурацию пользовательских дампов стека для отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="895a7-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="895a7-109">Метод EndCustomDump</span><span class="sxs-lookup"><span data-stu-id="895a7-109">EndCustomDump Method</span></span>](iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="895a7-110">Очищает конфигурацию пользовательского дампа стека, которая была задана предыдущим вызовом метода `BeginCustomDump` .</span><span class="sxs-lookup"><span data-stu-id="895a7-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="895a7-111">Метод GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="895a7-111">GetBucketParametersForCurrentException Method</span></span>](iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="895a7-112">Возвращает контейнер Watson для текущего исключения в вызывающем потоке.</span><span class="sxs-lookup"><span data-stu-id="895a7-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="895a7-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="895a7-113">Remarks</span></span>  

 <span data-ttu-id="895a7-114">`BeginCustomDump`Метод задает конфигурацию пользовательского дампа стека.</span><span class="sxs-lookup"><span data-stu-id="895a7-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="895a7-115">`EndCustomDump`Метод очищает конфигурацию дампа пользовательского стека и освобождает любое связанное состояние.</span><span class="sxs-lookup"><span data-stu-id="895a7-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="895a7-116">Он должен вызываться после завершения пользовательского дампа.</span><span class="sxs-lookup"><span data-stu-id="895a7-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="895a7-117">Сбой вызова `EndCustomDump` приводит к утечке памяти.</span><span class="sxs-lookup"><span data-stu-id="895a7-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="895a7-118">Требования</span><span class="sxs-lookup"><span data-stu-id="895a7-118">Requirements</span></span>  

 <span data-ttu-id="895a7-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="895a7-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="895a7-120">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="895a7-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="895a7-121">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="895a7-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="895a7-122">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="895a7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="895a7-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="895a7-123">See also</span></span>

- [<span data-ttu-id="895a7-124">Перечисление ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="895a7-124">ECustomDumpItemKind Enumeration</span></span>](ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="895a7-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="895a7-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
