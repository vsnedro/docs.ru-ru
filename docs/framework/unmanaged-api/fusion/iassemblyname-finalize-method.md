---
title: Метод IAssemblyName::Finalize
ms.date: 03/30/2017
api_name:
- IAssemblyName.Finalize
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::Finalize
helpviewer_keywords:
- Finalize method [.NET Framework fusion]
- IAssemblyName::Finalize method [.NET Framework fusion]
ms.assetid: 610e792d-98ef-411f-90b0-5b9a3813f547
topic_type:
- apiref
ms.openlocfilehash: 842b878fac1e2590eb6ea0b29ebee0d46e818474
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727930"
---
# <a name="iassemblynamefinalize-method"></a><span data-ttu-id="e50dc-102">Метод IAssemblyName::Finalize</span><span class="sxs-lookup"><span data-stu-id="e50dc-102">IAssemblyName::Finalize Method</span></span>

<span data-ttu-id="e50dc-103">Позволяет этому объекту [IAssemblyName](iassemblyname-interface.md) освобождать ресурсы и выполнять другие операции очистки перед вызовом деструктора.</span><span class="sxs-lookup"><span data-stu-id="e50dc-103">Allows this [IAssemblyName](iassemblyname-interface.md) object to release resources and perform other cleanup operations before its destructor is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e50dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e50dc-104">Syntax</span></span>  
  
```cpp  
HRESULT Finalize ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="e50dc-105">Требования</span><span class="sxs-lookup"><span data-stu-id="e50dc-105">Requirements</span></span>  

 <span data-ttu-id="e50dc-106">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e50dc-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e50dc-107">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="e50dc-107">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e50dc-108">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e50dc-108">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e50dc-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e50dc-109">See also</span></span>

- [<span data-ttu-id="e50dc-110">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="e50dc-110">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
