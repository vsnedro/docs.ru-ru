---
title: Функция _EFN_GetManagedExcepStack
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedExcepStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedExcepStack
helpviewer_keywords:
- _EFN_GetManagedExcepStack function [.NET Framework debugging]
ms.assetid: 21ceed9e-62b2-4024-b027-6d095109955a
topic_type:
- apiref
ms.openlocfilehash: b86277836b1be48c9f8020d59071aba8c5b1e457
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676248"
---
# <a name="_efn_getmanagedexcepstack-function"></a><span data-ttu-id="8ca1d-102">\_ЕФН \_ жетманажедексцепстакк, функция</span><span class="sxs-lookup"><span data-stu-id="8ca1d-102">\_EFN\_GetManagedExcepStack Function</span></span>

<span data-ttu-id="8ca1d-103">Учитывая адрес объекта управляемого исключения, возвращает строковую версию трассировки стека, содержащейся внутри.</span><span class="sxs-lookup"><span data-stu-id="8ca1d-103">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ca1d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ca1d-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ca1d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8ca1d-105">Parameters</span></span>  

 `Client`  
 <span data-ttu-id="8ca1d-106">окне Отлаживаемый клиент.</span><span class="sxs-lookup"><span data-stu-id="8ca1d-106">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="8ca1d-107">окне Указатель на управляемый объект, производный от <xref:System.Exception> .</span><span class="sxs-lookup"><span data-stu-id="8ca1d-107">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="8ca1d-108">сзстаккстринг</span><span class="sxs-lookup"><span data-stu-id="8ca1d-108">szStackString</span></span>  
 <span data-ttu-id="8ca1d-109">заполняет Возвращаемая строка.</span><span class="sxs-lookup"><span data-stu-id="8ca1d-109">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="8ca1d-110">заполняет Число символов, доступных в буфере строк.</span><span class="sxs-lookup"><span data-stu-id="8ca1d-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ca1d-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8ca1d-111">Remarks</span></span>  

 <span data-ttu-id="8ca1d-112">Если в текущем потоке нет управляемого кода, функция возвращает HRESULT SOS_E_NOMANAGEDCODE со значением устройства 0x82 и кодом ошибки 0x1000.</span><span class="sxs-lookup"><span data-stu-id="8ca1d-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ca1d-113">Требования</span><span class="sxs-lookup"><span data-stu-id="8ca1d-113">Requirements</span></span>  

 <span data-ttu-id="8ca1d-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ca1d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ca1d-115">**Заголовок:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="8ca1d-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="8ca1d-116">**Версия .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ca1d-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ca1d-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8ca1d-117">See also</span></span>

- [<span data-ttu-id="8ca1d-118">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="8ca1d-118">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
