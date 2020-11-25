---
title: Метод ICLRMetaHost::ExitProcess
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
ms.openlocfilehash: 6d601ac3ece801353b630c74ed852c2657f25d7f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730468"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="19afc-102">Метод ICLRMetaHost::ExitProcess</span><span class="sxs-lookup"><span data-stu-id="19afc-102">ICLRMetaHost::ExitProcess Method</span></span>

<span data-ttu-id="19afc-103">Пытается корректно завершить работу всех загруженных сред выполнения, а затем завершить процесс.</span><span class="sxs-lookup"><span data-stu-id="19afc-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="19afc-104">Заменяет функцию [корекситпроцесс](corexitprocess-function.md) .</span><span class="sxs-lookup"><span data-stu-id="19afc-104">Supersedes the [CorExitProcess](corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19afc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="19afc-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19afc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="19afc-106">Parameters</span></span>  

 `iExitCode`  
 <span data-ttu-id="19afc-107">окне Код выхода для процесса.</span><span class="sxs-lookup"><span data-stu-id="19afc-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19afc-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="19afc-108">Return Value</span></span>  

 <span data-ttu-id="19afc-109">Этот метод никогда не возвращает, поэтому возвращаемое значение не определено.</span><span class="sxs-lookup"><span data-stu-id="19afc-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19afc-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="19afc-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19afc-111">Требования</span><span class="sxs-lookup"><span data-stu-id="19afc-111">Requirements</span></span>  

 <span data-ttu-id="19afc-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19afc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19afc-113">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="19afc-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="19afc-114">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="19afc-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19afc-115">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19afc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19afc-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="19afc-116">See also</span></span>

- [<span data-ttu-id="19afc-117">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="19afc-117">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="19afc-118">Размещение</span><span class="sxs-lookup"><span data-stu-id="19afc-118">Hosting</span></span>](index.md)
