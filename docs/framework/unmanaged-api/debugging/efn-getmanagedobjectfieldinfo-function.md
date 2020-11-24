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
ms.openlocfilehash: 4c088b7e1096f8b4cad11a3e27b4045e233989ae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676222"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a><span data-ttu-id="4a53e-102">\_ЕФН \_ жетманажедобжектфиелдинфо, функция</span><span class="sxs-lookup"><span data-stu-id="4a53e-102">\_EFN\_GetManagedObjectFieldInfo Function</span></span>

<span data-ttu-id="4a53e-103">Возвращает смещение от начала объекта до поля и значение поля, используя предоставленный указатель объекта и имя поля.</span><span class="sxs-lookup"><span data-stu-id="4a53e-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a53e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a53e-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a53e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4a53e-105">Parameters</span></span>  

 `Client`  
 <span data-ttu-id="4a53e-106">окне Указатель на клиент отладки.</span><span class="sxs-lookup"><span data-stu-id="4a53e-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="4a53e-107">окне Указатель на управляемый объект.</span><span class="sxs-lookup"><span data-stu-id="4a53e-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="4a53e-108">сзфиелднаме</span><span class="sxs-lookup"><span data-stu-id="4a53e-108">szFieldName</span></span>  
 <span data-ttu-id="4a53e-109">окне Указатель управляемого объекта на имя поля.</span><span class="sxs-lookup"><span data-stu-id="4a53e-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="4a53e-110">заполняет Значение поля.</span><span class="sxs-lookup"><span data-stu-id="4a53e-110">[out] The field value.</span></span> <span data-ttu-id="4a53e-111">Этот параметр может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="4a53e-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="4a53e-112">заполняет Смещение от `objAddr` до поля.</span><span class="sxs-lookup"><span data-stu-id="4a53e-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="4a53e-113">Этот параметр может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="4a53e-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a53e-114">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4a53e-114">Remarks</span></span>  

 <span data-ttu-id="4a53e-115">Если смещение равно 0, смещение не записывается.</span><span class="sxs-lookup"><span data-stu-id="4a53e-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="4a53e-116">Если в текущем потоке нет управляемого кода, функция возвращает HRESULT SOS_E_NOMANAGEDCODE со значением устройства 0x82 и кодом ошибки 0x1000.</span><span class="sxs-lookup"><span data-stu-id="4a53e-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a53e-117">Требования</span><span class="sxs-lookup"><span data-stu-id="4a53e-117">Requirements</span></span>  

 <span data-ttu-id="4a53e-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a53e-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a53e-119">**Заголовок:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="4a53e-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="4a53e-120">**Версия .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a53e-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a53e-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4a53e-121">See also</span></span>

- [<span data-ttu-id="4a53e-122">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="4a53e-122">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
