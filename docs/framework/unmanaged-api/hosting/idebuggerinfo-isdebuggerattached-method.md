---
title: Метод IDebuggerInfo::IsDebuggerAttached
ms.date: 03/30/2017
api_name:
- IDebuggerInfo.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IsDebuggerAttached
helpviewer_keywords:
- IDebuggerInfo::IsDebuggerAttached method [.NET Framework hosting]
- IsDebuggerAttached method, IDebuggerInfo interface [.NET Framework hosting]
ms.assetid: 6e21872f-602f-411a-a423-bff5cdf27000
topic_type:
- apiref
ms.openlocfilehash: 95b7a2f6d35104c3353853549dacc783355feb5b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805332"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="fc3f1-102">Метод IDebuggerInfo::IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="fc3f1-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="fc3f1-103">Возвращает значение, указывающее, присоединен ли к этому процессу управляемый отладчик.</span><span class="sxs-lookup"><span data-stu-id="fc3f1-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc3f1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc3f1-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc3f1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc3f1-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="fc3f1-106">заполняет Указатель на значение, равное, `true` Если управляемый отладчик присоединен к процессу; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="fc3f1-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc3f1-107">Требования</span><span class="sxs-lookup"><span data-stu-id="fc3f1-107">Requirements</span></span>  
 <span data-ttu-id="fc3f1-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc3f1-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc3f1-109">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fc3f1-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fc3f1-110">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fc3f1-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc3f1-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc3f1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc3f1-112">См. также статью</span><span class="sxs-lookup"><span data-stu-id="fc3f1-112">See also</span></span>

- [<span data-ttu-id="fc3f1-113">Интерфейс IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="fc3f1-113">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)
