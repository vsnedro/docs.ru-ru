---
title: Интерфейс IInstallReferenceEnum
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum
helpviewer_keywords:
- IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type:
- apiref
ms.openlocfilehash: f56a9049cd4b503124abe9dd4866dc91779e268e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721068"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="3b762-102">Интерфейс IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="3b762-102">IInstallReferenceEnum Interface</span></span>

<span data-ttu-id="3b762-103">Представляет перечислитель для сборок, на которые имеются ссылки, установленных в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="3b762-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b762-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b762-104">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3b762-105">Методы</span><span class="sxs-lookup"><span data-stu-id="3b762-105">Methods</span></span>  
  
|<span data-ttu-id="3b762-106">Метод</span><span class="sxs-lookup"><span data-stu-id="3b762-106">Method</span></span>|<span data-ttu-id="3b762-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3b762-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3b762-108">Метод GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="3b762-108">GetNextInstallReferenceItem Method</span></span>](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="3b762-109">Возвращает указатель на следующий объект, `IInstallReferenceItem` содержащийся в этом `IInstallReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="3b762-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b762-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3b762-110">Requirements</span></span>  

 <span data-ttu-id="3b762-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b762-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b762-112">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="3b762-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3b762-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b762-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b762-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3b762-114">See also</span></span>

- [<span data-ttu-id="3b762-115">Fusion-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="3b762-115">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="3b762-116">Интерфейс IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="3b762-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
