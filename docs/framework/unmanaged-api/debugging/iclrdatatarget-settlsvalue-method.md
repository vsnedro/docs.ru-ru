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
ms.openlocfilehash: d2eaab1f42eb04d8e9727220a08842ca75a2eadf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723692"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="32e59-102">Метод ICLRDataTarget::SetTLSValue</span><span class="sxs-lookup"><span data-stu-id="32e59-102">ICLRDataTarget::SetTLSValue Method</span></span>

<span data-ttu-id="32e59-103">Задает значение в локальном хранилище потока (TLS) указанного потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="32e59-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="32e59-104">Этот метод вызывается службами доступа к данным среды CLR.</span><span class="sxs-lookup"><span data-stu-id="32e59-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32e59-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32e59-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32e59-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="32e59-106">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="32e59-107">окне Идентификатор операционной системы потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="32e59-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="32e59-108">окне Индекс расположения.</span><span class="sxs-lookup"><span data-stu-id="32e59-108">[in] The index of the location.</span></span> <span data-ttu-id="32e59-109">Это значение должно быть допустимым индексом в локальном хранилище указанного потока.</span><span class="sxs-lookup"><span data-stu-id="32e59-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="32e59-110">окне `CLRDATA_ADDRESS` Значение типа, указывающее значение, помещаемое в заданное расположение TLS.</span><span class="sxs-lookup"><span data-stu-id="32e59-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32e59-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="32e59-111">Remarks</span></span>  

 <span data-ttu-id="32e59-112">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="32e59-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32e59-113">Требования</span><span class="sxs-lookup"><span data-stu-id="32e59-113">Requirements</span></span>  

 <span data-ttu-id="32e59-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32e59-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32e59-115">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="32e59-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="32e59-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32e59-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32e59-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32e59-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32e59-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="32e59-118">See also</span></span>

- [<span data-ttu-id="32e59-119">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="32e59-119">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
