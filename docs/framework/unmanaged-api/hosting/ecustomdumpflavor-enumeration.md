---
title: Перечисление ECustomDumpFlavor
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
ms.openlocfilehash: 1b8440ed6e878aac3dd08d9f8ed528c93739a724
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686323"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="afe1c-102">Перечисление ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="afe1c-102">ECustomDumpFlavor Enumeration</span></span>

<span data-ttu-id="afe1c-103">Содержит значения, указывающие, какие элементы следует включать в пользовательское подмножество дампа кучи при сообщении об ошибках.</span><span class="sxs-lookup"><span data-stu-id="afe1c-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afe1c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="afe1c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="afe1c-105">Члены</span><span class="sxs-lookup"><span data-stu-id="afe1c-105">Members</span></span>  
  
|<span data-ttu-id="afe1c-106">Член</span><span class="sxs-lookup"><span data-stu-id="afe1c-106">Member</span></span>|<span data-ttu-id="afe1c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="afe1c-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="afe1c-108">Указывает, что дамп пользовательской кучи должен запускаться как Малый дамп и включать дополнительные данные, указанные любыми экземплярами [кустомдумпитем](customdumpitem-structure.md) , передаваемыми в один и тот же метод.</span><span class="sxs-lookup"><span data-stu-id="afe1c-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="afe1c-109">Указывает, что дамп пользовательской кучи должен собирать все данные состояния времени выполнения, которые не были выделены динамически.</span><span class="sxs-lookup"><span data-stu-id="afe1c-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afe1c-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="afe1c-110">Remarks</span></span>  

 <span data-ttu-id="afe1c-111">Параметр типа `ECustomDumpFlavor` передается методу [iclrerrorreportingmanagergetbucketparametersforcurrentexception:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) .</span><span class="sxs-lookup"><span data-stu-id="afe1c-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afe1c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="afe1c-112">Requirements</span></span>  

 <span data-ttu-id="afe1c-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afe1c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afe1c-114">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="afe1c-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="afe1c-115">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="afe1c-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="afe1c-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afe1c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afe1c-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="afe1c-117">See also</span></span>

- [<span data-ttu-id="afe1c-118">Перечисление ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="afe1c-118">ECustomDumpItemKind Enumeration</span></span>](ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="afe1c-119">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="afe1c-119">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="afe1c-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="afe1c-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
