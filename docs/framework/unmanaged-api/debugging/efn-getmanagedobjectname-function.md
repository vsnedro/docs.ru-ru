---
title: Функция _EFN_GetManagedObjectName
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectName
helpviewer_keywords:
- _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type:
- apiref
ms.openlocfilehash: 0fb694cf85256c0f3ac5ae179e53ff504ab707e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676209"
---
# <a name="_efn_getmanagedobjectname-function"></a><span data-ttu-id="b5dd5-102">\_ЕФН \_ жетманажедобжектнаме, функция</span><span class="sxs-lookup"><span data-stu-id="b5dd5-102">\_EFN\_GetManagedObjectName Function</span></span>

<span data-ttu-id="b5dd5-103">Возвращает имя типа, используя предоставленный указатель управляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="b5dd5-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5dd5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5dd5-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5dd5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b5dd5-105">Parameters</span></span>  

 `Client`  
 <span data-ttu-id="b5dd5-106">окне Указатель на клиент отладки.</span><span class="sxs-lookup"><span data-stu-id="b5dd5-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="b5dd5-107">окне Указатель на управляемый объект.</span><span class="sxs-lookup"><span data-stu-id="b5dd5-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="b5dd5-108">szName</span><span class="sxs-lookup"><span data-stu-id="b5dd5-108">szName</span></span>  
 <span data-ttu-id="b5dd5-109">заполняет Имя типа.</span><span class="sxs-lookup"><span data-stu-id="b5dd5-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="b5dd5-110">заполняет Число символов, доступных в буфере строк.</span><span class="sxs-lookup"><span data-stu-id="b5dd5-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5dd5-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b5dd5-111">Remarks</span></span>  

 <span data-ttu-id="b5dd5-112">Если в текущем потоке нет управляемого кода, функция возвращает HRESULT SOS_E_NOMANAGEDCODE со значением устройства 0x82 и кодом ошибки 0x1000.</span><span class="sxs-lookup"><span data-stu-id="b5dd5-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5dd5-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b5dd5-113">Requirements</span></span>  

 <span data-ttu-id="b5dd5-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5dd5-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5dd5-115">**Заголовок:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="b5dd5-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="b5dd5-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5dd5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5dd5-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b5dd5-117">See also</span></span>

- [<span data-ttu-id="b5dd5-118">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="b5dd5-118">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
