---
title: Метод ICLRDataTarget::Request
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
ms.openlocfilehash: 4d0cf22b4b0644d6b25d6b3ef884718cb9ca1e42
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723796"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="f47a2-102">Метод ICLRDataTarget::Request</span><span class="sxs-lookup"><span data-stu-id="f47a2-102">ICLRDataTarget::Request Method</span></span>

<span data-ttu-id="f47a2-103">Вызывается службами доступа к данным среды CLR для запроса операции, как определено в реализации.</span><span class="sxs-lookup"><span data-stu-id="f47a2-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f47a2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f47a2-104">Syntax</span></span>  
  
```cpp  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]
        BYTE                *outBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f47a2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f47a2-105">Parameters</span></span>  

 `reqCode`  
 <span data-ttu-id="f47a2-106">окне Определяется пользователем.</span><span class="sxs-lookup"><span data-stu-id="f47a2-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="f47a2-107">окне Размер входного буфера, используемого для входящего запроса.</span><span class="sxs-lookup"><span data-stu-id="f47a2-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="f47a2-108">окне Буфер, содержащий запрос.</span><span class="sxs-lookup"><span data-stu-id="f47a2-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="f47a2-109">окне Размер выходного буфера, используемого для ответа.</span><span class="sxs-lookup"><span data-stu-id="f47a2-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="f47a2-110">заполняет Буфер, содержащий ответ.</span><span class="sxs-lookup"><span data-stu-id="f47a2-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f47a2-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f47a2-111">Remarks</span></span>  

 <span data-ttu-id="f47a2-112">`Request`Метод упрощает добавление неуказанных пользовательских операций.</span><span class="sxs-lookup"><span data-stu-id="f47a2-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="f47a2-113">Это значит, что этот метод обеспечивает расширяемость без необходимости пересмотра определения интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f47a2-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="f47a2-114">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="f47a2-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f47a2-115">Требования</span><span class="sxs-lookup"><span data-stu-id="f47a2-115">Requirements</span></span>  

 <span data-ttu-id="f47a2-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f47a2-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f47a2-117">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="f47a2-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f47a2-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f47a2-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f47a2-119">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f47a2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f47a2-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f47a2-120">See also</span></span>

- [<span data-ttu-id="f47a2-121">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="f47a2-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
