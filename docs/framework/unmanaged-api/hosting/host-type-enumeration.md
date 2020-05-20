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
ms.openlocfilehash: e8dda83df8a320733f45dbcc13599cdf37d26492
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617156"
---
# <a name="host_type-enumeration"></a><span data-ttu-id="90e10-102">Перечисление HOST_TYPE</span><span class="sxs-lookup"><span data-stu-id="90e10-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="90e10-103">Содержит значения, указывающие тип узла, запускающего приложение.</span><span class="sxs-lookup"><span data-stu-id="90e10-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90e10-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90e10-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="90e10-105">Участники</span><span class="sxs-lookup"><span data-stu-id="90e10-105">Members</span></span>  
  
|<span data-ttu-id="90e10-106">Член</span><span class="sxs-lookup"><span data-stu-id="90e10-106">Member</span></span>|<span data-ttu-id="90e10-107">Описание</span><span class="sxs-lookup"><span data-stu-id="90e10-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="90e10-108">Запустите приложение из Апплаунч. exe.</span><span class="sxs-lookup"><span data-stu-id="90e10-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="90e10-109">Используйте это значение для частично доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="90e10-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="90e10-110">Запустите приложение напрямую.</span><span class="sxs-lookup"><span data-stu-id="90e10-110">Launch the application directly.</span></span> <span data-ttu-id="90e10-111">То есть запустите приложение из собственного EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="90e10-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="90e10-112">Используйте это значение для полностью доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="90e10-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="90e10-113">То же, что и HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="90e10-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="90e10-114">Требования</span><span class="sxs-lookup"><span data-stu-id="90e10-114">Requirements</span></span>  
 <span data-ttu-id="90e10-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90e10-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90e10-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="90e10-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="90e10-117">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="90e10-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90e10-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90e10-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90e10-119">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="90e10-119">See also</span></span>

- [<span data-ttu-id="90e10-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="90e10-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
