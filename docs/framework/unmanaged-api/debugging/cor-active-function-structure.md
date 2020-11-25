---
title: Структура COR_ACTIVE_FUNCTION
ms.date: 03/30/2017
api_name:
- COR_ACTIVE_FUNCTION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ACTIVE_FUNCTION
helpviewer_keywords:
- COR_ACTIVE_FUNCTION structure [.NET Framework debugging]
ms.assetid: ed86185f-2152-459c-961f-10c06d62e83f
topic_type:
- apiref
ms.openlocfilehash: c50ba530d78296ebb956329b2f34b4f1e5cae94c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727423"
---
# <a name="cor_active_function-structure"></a><span data-ttu-id="eb7e0-102">Структура COR_ACTIVE_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="eb7e0-102">COR_ACTIVE_FUNCTION Structure</span></span>

<span data-ttu-id="eb7e0-103">Содержит сведения о функциях, которые в данный момент активны в кадрах потока.</span><span class="sxs-lookup"><span data-stu-id="eb7e0-103">Contains information about the functions that are currently active in a thread's frames.</span></span> <span data-ttu-id="eb7e0-104">Эта структура используется методом [ICorDebugThread2:: GetActiveFunctions](icordebugthread2-getactivefunctions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eb7e0-104">This structure is used by the [ICorDebugThread2::GetActiveFunctions](icordebugthread2-getactivefunctions-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb7e0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb7e0-105">Syntax</span></span>  
  
```cpp  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="eb7e0-106">Члены</span><span class="sxs-lookup"><span data-stu-id="eb7e0-106">Members</span></span>  
  
|<span data-ttu-id="eb7e0-107">Член</span><span class="sxs-lookup"><span data-stu-id="eb7e0-107">Member</span></span>|<span data-ttu-id="eb7e0-108">Описание</span><span class="sxs-lookup"><span data-stu-id="eb7e0-108">Description</span></span>|  
|------------|-----------------|  
|`pAppDomain`|<span data-ttu-id="eb7e0-109">Указатель на владельца домена приложения для `ilOffset` поля.</span><span class="sxs-lookup"><span data-stu-id="eb7e0-109">Pointer to the application domain owner of the `ilOffset` field.</span></span>|  
|`pModule`|<span data-ttu-id="eb7e0-110">Указатель на владельца `ilOffset` поля.</span><span class="sxs-lookup"><span data-stu-id="eb7e0-110">Pointer to the module owner of the `ilOffset` field.</span></span>|  
|`pFunction`|<span data-ttu-id="eb7e0-111">Указатель на владельца функции `ilOffset` поля.</span><span class="sxs-lookup"><span data-stu-id="eb7e0-111">Pointer to the function owner of the `ilOffset` field.</span></span>|  
|`ilOffset`|<span data-ttu-id="eb7e0-112">Смещение кадра на языке MSIL.</span><span class="sxs-lookup"><span data-stu-id="eb7e0-112">The Microsoft intermediate language (MSIL) offset of the frame.</span></span>|  
|`flags`|<span data-ttu-id="eb7e0-113">Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="eb7e0-113">Reserved for future extensibility.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eb7e0-114">Требования</span><span class="sxs-lookup"><span data-stu-id="eb7e0-114">Requirements</span></span>  

 <span data-ttu-id="eb7e0-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb7e0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb7e0-116">**Заголовок:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="eb7e0-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="eb7e0-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb7e0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb7e0-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb7e0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb7e0-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="eb7e0-119">See also</span></span>

- [<span data-ttu-id="eb7e0-120">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="eb7e0-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="eb7e0-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="eb7e0-121">Debugging</span></span>](index.md)
