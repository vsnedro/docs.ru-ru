---
title: Структура StackOverflowInfo
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
ms.openlocfilehash: 941093b9a0856c2b716ba359c854473f3c9ea26a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006523"
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="d17fb-102">Структура StackOverflowInfo</span><span class="sxs-lookup"><span data-stu-id="d17fb-102">StackOverflowInfo Structure</span></span>
<span data-ttu-id="d17fb-103">Хранит тип произошедшего переполнения и сведения об исключении, порождаемом из-за переполнения.</span><span class="sxs-lookup"><span data-stu-id="d17fb-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d17fb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d17fb-104">Syntax</span></span>  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="d17fb-105">Участники</span><span class="sxs-lookup"><span data-stu-id="d17fb-105">Members</span></span>  
  
|<span data-ttu-id="d17fb-106">Член</span><span class="sxs-lookup"><span data-stu-id="d17fb-106">Member</span></span>|<span data-ttu-id="d17fb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d17fb-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="d17fb-108">Значение перечисления [StackOverflowType](stackoverflowtype-enumeration.md) , указывающее тип переполнения.</span><span class="sxs-lookup"><span data-stu-id="d17fb-108">A value of the [StackOverflowType](stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="d17fb-109">Указатель на `EXCEPTION_POINTERS` объект Win32, который содержит запись исключения с независимым от компьютера описанием исключения и записью контекста с зависящим от компьютера описанием контекста процессора на момент возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="d17fb-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d17fb-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="d17fb-110">Remarks</span></span>  
 <span data-ttu-id="d17fb-111">`StackOverflowInfo`Объект передается в метод [иактиононклревент:: oneven](iactiononclrevent-onevent-method.md) для `Event_StackOverflow` событий.</span><span class="sxs-lookup"><span data-stu-id="d17fb-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d17fb-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d17fb-112">Requirements</span></span>  
 <span data-ttu-id="d17fb-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d17fb-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d17fb-114">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="d17fb-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="d17fb-115">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d17fb-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d17fb-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d17fb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d17fb-117">См. также статью</span><span class="sxs-lookup"><span data-stu-id="d17fb-117">See also</span></span>

- [<span data-ttu-id="d17fb-118">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="d17fb-118">Hosting Structures</span></span>](hosting-structures.md)
