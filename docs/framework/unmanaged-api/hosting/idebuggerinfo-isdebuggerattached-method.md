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
ms.openlocfilehash: 28b0c5ad5ed8b706974399dcd5468e9810b9fd57
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721703"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="f5c20-102">Метод IDebuggerInfo::IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="f5c20-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>

<span data-ttu-id="f5c20-103">Возвращает значение, указывающее, присоединен ли к этому процессу управляемый отладчик.</span><span class="sxs-lookup"><span data-stu-id="f5c20-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5c20-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5c20-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5c20-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f5c20-105">Parameters</span></span>  

 `pbAttached`  
 <span data-ttu-id="f5c20-106">заполняет Указатель на значение, равное, `true` Если управляемый отладчик присоединен к процессу; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="f5c20-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5c20-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f5c20-107">Requirements</span></span>  

 <span data-ttu-id="f5c20-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5c20-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5c20-109">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f5c20-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f5c20-110">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f5c20-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5c20-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5c20-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5c20-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f5c20-112">See also</span></span>

- [<span data-ttu-id="f5c20-113">Интерфейс IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="f5c20-113">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)
