---
title: Структура CustomDumpItem
ms.date: 03/30/2017
api_name:
- CustomDumpItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CustomDumpItem
helpviewer_keywords:
- CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type:
- apiref
ms.openlocfilehash: 5c77a332593ba470d2e29b87cba182a770d5db7e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616441"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="2a6b9-102">Структура CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="2a6b9-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="2a6b9-103">Описывает элемент, добавляемый в пользовательский дамп в отчетах об ошибках.</span><span class="sxs-lookup"><span data-stu-id="2a6b9-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a6b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a6b9-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="2a6b9-105">Участники</span><span class="sxs-lookup"><span data-stu-id="2a6b9-105">Members</span></span>  
  
|<span data-ttu-id="2a6b9-106">Член</span><span class="sxs-lookup"><span data-stu-id="2a6b9-106">Member</span></span>|<span data-ttu-id="2a6b9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2a6b9-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="2a6b9-108">Значение [екустомдумпитемкинд](ecustomdumpitemkind-enumeration.md) , указывающее тип добавляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="2a6b9-108">An [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="2a6b9-109">В настоящий момент не используется.</span><span class="sxs-lookup"><span data-stu-id="2a6b9-109">Not currently used.</span></span> <span data-ttu-id="2a6b9-110">Все элементы, добавляемые в объединение, не должны быть больше размера указателя.</span><span class="sxs-lookup"><span data-stu-id="2a6b9-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="2a6b9-111">Если `struct` требуется, необходимо выделить его отдельно и указать на него.</span><span class="sxs-lookup"><span data-stu-id="2a6b9-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a6b9-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2a6b9-112">Remarks</span></span>  
 <span data-ttu-id="2a6b9-113">[Iclrerrorreportingmanagergetbucketparametersforcurrentexception:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) принимает параметр типа `CustomDumpItem` .</span><span class="sxs-lookup"><span data-stu-id="2a6b9-113">[ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a6b9-114">Требования</span><span class="sxs-lookup"><span data-stu-id="2a6b9-114">Requirements</span></span>  
 <span data-ttu-id="2a6b9-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a6b9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a6b9-116">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="2a6b9-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="2a6b9-117">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2a6b9-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a6b9-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a6b9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a6b9-119">См. также статью</span><span class="sxs-lookup"><span data-stu-id="2a6b9-119">See also</span></span>

- [<span data-ttu-id="2a6b9-120">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="2a6b9-120">Hosting Structures</span></span>](hosting-structures.md)
