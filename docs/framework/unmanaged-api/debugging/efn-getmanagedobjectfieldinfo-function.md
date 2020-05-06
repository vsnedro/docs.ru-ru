---
title: Функция _EFN_GetManagedObjectFieldInfo
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
ms.openlocfilehash: 42f7020212dd2db793b7c7d20a15c129157e7261
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860768"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a><span data-ttu-id="15cf4-102">\_ЕФН\_Жетманажедобжектфиелдинфо, функция</span><span class="sxs-lookup"><span data-stu-id="15cf4-102">\_EFN\_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="15cf4-103">Возвращает смещение от начала объекта до поля и значение поля, используя предоставленный указатель объекта и имя поля.</span><span class="sxs-lookup"><span data-stu-id="15cf4-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15cf4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15cf4-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15cf4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="15cf4-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="15cf4-106">окне Указатель на клиент отладки.</span><span class="sxs-lookup"><span data-stu-id="15cf4-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="15cf4-107">окне Указатель на управляемый объект.</span><span class="sxs-lookup"><span data-stu-id="15cf4-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="15cf4-108">сзфиелднаме</span><span class="sxs-lookup"><span data-stu-id="15cf4-108">szFieldName</span></span>  
 <span data-ttu-id="15cf4-109">окне Указатель управляемого объекта на имя поля.</span><span class="sxs-lookup"><span data-stu-id="15cf4-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="15cf4-110">заполняет Значение поля.</span><span class="sxs-lookup"><span data-stu-id="15cf4-110">[out] The field value.</span></span> <span data-ttu-id="15cf4-111">Этот параметр может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="15cf4-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="15cf4-112">заполняет Смещение от `objAddr` до поля.</span><span class="sxs-lookup"><span data-stu-id="15cf4-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="15cf4-113">Этот параметр может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="15cf4-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15cf4-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="15cf4-114">Remarks</span></span>  
 <span data-ttu-id="15cf4-115">Если смещение равно 0, смещение не записывается.</span><span class="sxs-lookup"><span data-stu-id="15cf4-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="15cf4-116">Если в текущем потоке нет управляемого кода, функция возвращает HRESULT SOS_E_NOMANAGEDCODE со значением устройства 0x82 и кодом ошибки 0x1000.</span><span class="sxs-lookup"><span data-stu-id="15cf4-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15cf4-117">Требования</span><span class="sxs-lookup"><span data-stu-id="15cf4-117">Requirements</span></span>  
 <span data-ttu-id="15cf4-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15cf4-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15cf4-119">**Заголовок:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="15cf4-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="15cf4-120">**Версия .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15cf4-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15cf4-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="15cf4-121">See also</span></span>

- [<span data-ttu-id="15cf4-122">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="15cf4-122">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
