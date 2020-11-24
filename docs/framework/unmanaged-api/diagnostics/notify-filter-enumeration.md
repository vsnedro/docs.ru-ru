---
title: Перечисление NOTIFY_FILTER
ms.date: 03/30/2017
api_name:
- NOTIFY_FILTER
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- NOTIFY_FILTER
helpviewer_keywords:
- NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type:
- apiref
ms.openlocfilehash: 365bc0dc73b04d3afd171c40f336432f77552b6d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690958"
---
# <a name="notify_filter-enumeration"></a><span data-ttu-id="e4e68-102">Перечисление NOTIFY_FILTER</span><span class="sxs-lookup"><span data-stu-id="e4e68-102">NOTIFY_FILTER Enumeration</span></span>

<span data-ttu-id="e4e68-103">Определяет обратные вызовы для функций отладчика.</span><span class="sxs-lookup"><span data-stu-id="e4e68-103">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="e4e68-104">Дополнительные сведения см. в описании метода [INotifySource2:: сетнотифифилтер](inotifysource2-setnotifyfilter-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e4e68-104">For more information, see the [INotifySource2::SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4e68-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4e68-105">Syntax</span></span>  
  
```cpp  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a><span data-ttu-id="e4e68-106">Члены</span><span class="sxs-lookup"><span data-stu-id="e4e68-106">Members</span></span>  
  
|<span data-ttu-id="e4e68-107">Член</span><span class="sxs-lookup"><span data-stu-id="e4e68-107">Member</span></span>|<span data-ttu-id="e4e68-108">Описание</span><span class="sxs-lookup"><span data-stu-id="e4e68-108">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="e4e68-109">Указывает, что должен быть вызван метод [INotifySink2:: OnSyncCallOut](inotifysink2-onsynccallout-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e4e68-109">Indicates that the [INotifySink2::OnSyncCallOut](inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="e4e68-110">Указывает, что должен быть вызван метод [INotifySink2:: OnSyncCallEnter](inotifysink2-onsynccallenter-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e4e68-110">Indicates that the [INotifySink2::OnSyncCallEnter](inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="e4e68-111">Указывает, что должен быть вызван метод [INotifySink2:: онсинккаллексит](inotifysink2-onsynccallexit-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e4e68-111">Indicates that the [INotifySink2::OnSyncCallExit](inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="e4e68-112">Указывает, что должен быть вызван метод [INotifySink2:: онсинккаллретурн](inotifysink2-onsynccallreturn-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e4e68-112">Indicates that the [INotifySink2::OnSyncCallReturn](inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="e4e68-113">Указывает, что должны быть вызваны все методы [INotifySink2](inotifysink2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e4e68-113">Indicates that all of the [INotifySink2](inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="e4e68-114">Активирует все существующие и будущие уведомления.</span><span class="sxs-lookup"><span data-stu-id="e4e68-114">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="e4e68-115">Указывает, что методы уведомления вызывать не нужно.</span><span class="sxs-lookup"><span data-stu-id="e4e68-115">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e4e68-116">Требования</span><span class="sxs-lookup"><span data-stu-id="e4e68-116">Requirements</span></span>  

 <span data-ttu-id="e4e68-117">**Заголовок:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="e4e68-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4e68-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e4e68-118">See also</span></span>

- [<span data-ttu-id="e4e68-119">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="e4e68-119">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
