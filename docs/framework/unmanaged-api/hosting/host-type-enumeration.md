---
title: Перечисление HOST_TYPE
ms.date: 03/30/2017
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
ms.openlocfilehash: 31640ada28af8e35554b91d5931d427fbaa8dcbe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721859"
---
# <a name="host_type-enumeration"></a><span data-ttu-id="e2b4f-102">Перечисление HOST_TYPE</span><span class="sxs-lookup"><span data-stu-id="e2b4f-102">HOST_TYPE Enumeration</span></span>

<span data-ttu-id="e2b4f-103">Содержит значения, указывающие тип узла, запускающего приложение.</span><span class="sxs-lookup"><span data-stu-id="e2b4f-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2b4f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2b4f-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="e2b4f-105">Члены</span><span class="sxs-lookup"><span data-stu-id="e2b4f-105">Members</span></span>  
  
|<span data-ttu-id="e2b4f-106">Член</span><span class="sxs-lookup"><span data-stu-id="e2b4f-106">Member</span></span>|<span data-ttu-id="e2b4f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e2b4f-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="e2b4f-108">Запустите приложение из AppLaunch.exe.</span><span class="sxs-lookup"><span data-stu-id="e2b4f-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="e2b4f-109">Используйте это значение для частично доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="e2b4f-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="e2b4f-110">Запустите приложение напрямую.</span><span class="sxs-lookup"><span data-stu-id="e2b4f-110">Launch the application directly.</span></span> <span data-ttu-id="e2b4f-111">То есть запустите приложение из собственного EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="e2b4f-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="e2b4f-112">Используйте это значение для полностью доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="e2b4f-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="e2b4f-113">То же, что и HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="e2b4f-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e2b4f-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e2b4f-114">Requirements</span></span>  

 <span data-ttu-id="e2b4f-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2b4f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2b4f-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e2b4f-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2b4f-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e2b4f-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2b4f-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2b4f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2b4f-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e2b4f-119">See also</span></span>

- [<span data-ttu-id="e2b4f-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="e2b4f-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
