---
title: Метод IAssemblyCacheItem::Commit
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.Commit
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::Commit
helpviewer_keywords:
- IAssemblyCacheItem::Commit method [.NET Framework fusion]
- Commit method, IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: c2321f17-f46f-4815-ae41-b28678753613
topic_type:
- apiref
ms.openlocfilehash: 2b7c10e82aca2b2ece7ea4d7209c1f3c9a456434
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670411"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="630c4-102">Метод IAssemblyCacheItem::Commit</span><span class="sxs-lookup"><span data-stu-id="630c4-102">IAssemblyCacheItem::Commit Method</span></span>

<span data-ttu-id="630c4-103">Фиксирует в памяти ссылку на кэшированную сборку.</span><span class="sxs-lookup"><span data-stu-id="630c4-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="630c4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="630c4-104">Syntax</span></span>  
  
```cpp  
HRESULT Commit (  
    [in] DWORD dwFlags,
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="630c4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="630c4-105">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="630c4-106">окне Флаги, определенные в Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="630c4-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="630c4-107">[out, необязательно] Значение, указывающее результат операции.</span><span class="sxs-lookup"><span data-stu-id="630c4-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="630c4-108">Требования</span><span class="sxs-lookup"><span data-stu-id="630c4-108">Requirements</span></span>  

 <span data-ttu-id="630c4-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="630c4-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="630c4-110">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="630c4-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="630c4-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="630c4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="630c4-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="630c4-112">See also</span></span>

- [<span data-ttu-id="630c4-113">Интерфейс IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="630c4-113">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
