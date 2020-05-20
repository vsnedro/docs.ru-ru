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
ms.openlocfilehash: 9b4c1187945b4c243375a3096c3a8a3b22599aef
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616285"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="7be0f-102">Перечисление ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="7be0f-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="7be0f-103">Содержит значения, указывающие, какие элементы следует включать в пользовательское подмножество дампа кучи при сообщении об ошибках.</span><span class="sxs-lookup"><span data-stu-id="7be0f-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7be0f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7be0f-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="7be0f-105">Участники</span><span class="sxs-lookup"><span data-stu-id="7be0f-105">Members</span></span>  
  
|<span data-ttu-id="7be0f-106">Член</span><span class="sxs-lookup"><span data-stu-id="7be0f-106">Member</span></span>|<span data-ttu-id="7be0f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7be0f-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="7be0f-108">Указывает, что дамп пользовательской кучи должен запускаться как Малый дамп и включать дополнительные данные, указанные любыми экземплярами [кустомдумпитем](customdumpitem-structure.md) , передаваемыми в один и тот же метод.</span><span class="sxs-lookup"><span data-stu-id="7be0f-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="7be0f-109">Указывает, что дамп пользовательской кучи должен собирать все данные состояния времени выполнения, которые не были выделены динамически.</span><span class="sxs-lookup"><span data-stu-id="7be0f-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7be0f-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="7be0f-110">Remarks</span></span>  
 <span data-ttu-id="7be0f-111">Параметр типа `ECustomDumpFlavor` передается методу [iclrerrorreportingmanagergetbucketparametersforcurrentexception:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7be0f-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7be0f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="7be0f-112">Requirements</span></span>  
 <span data-ttu-id="7be0f-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7be0f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7be0f-114">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7be0f-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7be0f-115">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7be0f-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7be0f-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7be0f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7be0f-117">См. также статью</span><span class="sxs-lookup"><span data-stu-id="7be0f-117">See also</span></span>

- [<span data-ttu-id="7be0f-118">Перечисление ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="7be0f-118">ECustomDumpItemKind Enumeration</span></span>](ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="7be0f-119">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="7be0f-119">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="7be0f-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="7be0f-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
