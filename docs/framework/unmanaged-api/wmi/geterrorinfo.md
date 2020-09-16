---
title: Функция Жетерроринфо (Справочник по неуправляемым API)
description: Функция Жетерроринфо получает сведения об ошибке из предыдущего вызова функции.
ms.date: 11/06/2017
api_name:
- GetErrorInfo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetErrorInfo
helpviewer_keywords:
- GetErrorInfo function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 9a80c0b5522113e704336cda29362a0406077931
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553679"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="b684e-103">Функция GetErrorInfo</span><span class="sxs-lookup"><span data-stu-id="b684e-103">GetErrorInfo function</span></span>
<span data-ttu-id="b684e-104">Получает сведения об ошибках из предыдущего вызова функции.</span><span class="sxs-lookup"><span data-stu-id="b684e-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="b684e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b684e-105">Syntax</span></span>  
  
```cpp  
IErrorInfo* GetErrorInfo();
```  

## <a name="return-value"></a><span data-ttu-id="b684e-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b684e-106">Return value</span></span>

<span data-ttu-id="b684e-107">Указатель на объект [IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) при успешном вызове функции или в `null` случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="b684e-107">An pointer to an [IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b684e-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="b684e-108">Remarks</span></span>

<span data-ttu-id="b684e-109">Эта функция заключает в оболочку вызов метода [икомсреадингинфо:: жетерроринфо](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) .</span><span class="sxs-lookup"><span data-stu-id="b684e-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b684e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b684e-110">Requirements</span></span>  
 <span data-ttu-id="b684e-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b684e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b684e-112">**Заголовок:** WMINet_Utils. def</span><span class="sxs-lookup"><span data-stu-id="b684e-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="b684e-113">**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b684e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b684e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b684e-114">See also</span></span>

- [<span data-ttu-id="b684e-115">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="b684e-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
