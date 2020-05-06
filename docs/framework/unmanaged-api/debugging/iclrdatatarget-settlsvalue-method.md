---
title: Метод ICLRDataTarget::SetTLSValue
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
ms.openlocfilehash: 6c98fc93fd659ccfc0ccd42eec7d95382cf342f8
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860511"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="1dd44-102">Метод ICLRDataTarget::SetTLSValue</span><span class="sxs-lookup"><span data-stu-id="1dd44-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="1dd44-103">Задает значение в локальном хранилище потока (TLS) указанного потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="1dd44-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="1dd44-104">Этот метод вызывается службами доступа к данным среды CLR.</span><span class="sxs-lookup"><span data-stu-id="1dd44-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dd44-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1dd44-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1dd44-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1dd44-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="1dd44-107">окне Идентификатор операционной системы потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="1dd44-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="1dd44-108">окне Индекс расположения.</span><span class="sxs-lookup"><span data-stu-id="1dd44-108">[in] The index of the location.</span></span> <span data-ttu-id="1dd44-109">Это значение должно быть допустимым индексом в локальном хранилище указанного потока.</span><span class="sxs-lookup"><span data-stu-id="1dd44-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="1dd44-110">окне Значение `CLRDATA_ADDRESS` типа, указывающее значение, помещаемое в заданное расположение TLS.</span><span class="sxs-lookup"><span data-stu-id="1dd44-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1dd44-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="1dd44-111">Remarks</span></span>  
 <span data-ttu-id="1dd44-112">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="1dd44-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dd44-113">Требования</span><span class="sxs-lookup"><span data-stu-id="1dd44-113">Requirements</span></span>  
 <span data-ttu-id="1dd44-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1dd44-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dd44-115">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="1dd44-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="1dd44-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1dd44-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1dd44-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dd44-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dd44-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1dd44-118">See also</span></span>

- [<span data-ttu-id="1dd44-119">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="1dd44-119">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
