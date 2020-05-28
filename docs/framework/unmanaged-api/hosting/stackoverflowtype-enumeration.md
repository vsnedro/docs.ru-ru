---
title: Перечисление StackOverflowType
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
ms.openlocfilehash: f399d33dbe05cb5768aa45533ef30d28409e18e2
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006484"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="1de93-102">Перечисление StackOverflowType</span><span class="sxs-lookup"><span data-stu-id="1de93-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="1de93-103">Содержит значения, указывающие основную причину события переполнения стека.</span><span class="sxs-lookup"><span data-stu-id="1de93-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1de93-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1de93-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="1de93-105">Участники</span><span class="sxs-lookup"><span data-stu-id="1de93-105">Members</span></span>  
  
|<span data-ttu-id="1de93-106">Член</span><span class="sxs-lookup"><span data-stu-id="1de93-106">Member</span></span>|<span data-ttu-id="1de93-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1de93-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="1de93-108">Переполнение стека было вызвано подсистемой выполнения.</span><span class="sxs-lookup"><span data-stu-id="1de93-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="1de93-109">Переполнение стека было вызвано управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="1de93-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="1de93-110">Переполнение стека было вызвано неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="1de93-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1de93-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="1de93-111">Remarks</span></span>  
 <span data-ttu-id="1de93-112">Эти сведения передаются на узел посредством вызова метода [иактиононклревент:: oneven](iactiononclrevent-onevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1de93-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1de93-113">Требования</span><span class="sxs-lookup"><span data-stu-id="1de93-113">Requirements</span></span>  
 <span data-ttu-id="1de93-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1de93-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1de93-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1de93-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1de93-116">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1de93-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1de93-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1de93-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1de93-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="1de93-118">See also</span></span>

- [<span data-ttu-id="1de93-119">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="1de93-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
