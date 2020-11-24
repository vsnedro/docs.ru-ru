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
ms.openlocfilehash: c77e93686c7d121e9fe2a92f03970404ab823dc0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673245"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="759b4-102">Структура CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="759b4-102">CustomDumpItem Structure</span></span>

<span data-ttu-id="759b4-103">Описывает элемент, добавляемый в пользовательский дамп в отчетах об ошибках.</span><span class="sxs-lookup"><span data-stu-id="759b4-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="759b4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="759b4-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="759b4-105">Члены</span><span class="sxs-lookup"><span data-stu-id="759b4-105">Members</span></span>  
  
|<span data-ttu-id="759b4-106">Член</span><span class="sxs-lookup"><span data-stu-id="759b4-106">Member</span></span>|<span data-ttu-id="759b4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="759b4-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="759b4-108">Значение [екустомдумпитемкинд](ecustomdumpitemkind-enumeration.md) , указывающее тип добавляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="759b4-108">An [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="759b4-109">В настоящий момент не используется.</span><span class="sxs-lookup"><span data-stu-id="759b4-109">Not currently used.</span></span> <span data-ttu-id="759b4-110">Все элементы, добавляемые в объединение, не должны быть больше размера указателя.</span><span class="sxs-lookup"><span data-stu-id="759b4-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="759b4-111">Если `struct` требуется, необходимо выделить его отдельно и указать на него.</span><span class="sxs-lookup"><span data-stu-id="759b4-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="759b4-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="759b4-112">Remarks</span></span>  

 <span data-ttu-id="759b4-113">[Iclrerrorreportingmanagergetbucketparametersforcurrentexception:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) принимает параметр типа `CustomDumpItem` .</span><span class="sxs-lookup"><span data-stu-id="759b4-113">[ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="759b4-114">Требования</span><span class="sxs-lookup"><span data-stu-id="759b4-114">Requirements</span></span>  

 <span data-ttu-id="759b4-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="759b4-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="759b4-116">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="759b4-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="759b4-117">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="759b4-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="759b4-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="759b4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="759b4-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="759b4-119">See also</span></span>

- [<span data-ttu-id="759b4-120">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="759b4-120">Hosting Structures</span></span>](hosting-structures.md)
