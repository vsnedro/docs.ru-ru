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
ms.openlocfilehash: b913affb4728dc80ba67438384cbeac87265f76d
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860539"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="359c7-102">Метод ICLRDataTarget::Request</span><span class="sxs-lookup"><span data-stu-id="359c7-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="359c7-103">Вызывается службами доступа к данным среды CLR для запроса операции, как определено в реализации.</span><span class="sxs-lookup"><span data-stu-id="359c7-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="359c7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="359c7-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="359c7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="359c7-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="359c7-106">окне Определяется пользователем.</span><span class="sxs-lookup"><span data-stu-id="359c7-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="359c7-107">окне Размер входного буфера, используемого для входящего запроса.</span><span class="sxs-lookup"><span data-stu-id="359c7-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="359c7-108">окне Буфер, содержащий запрос.</span><span class="sxs-lookup"><span data-stu-id="359c7-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="359c7-109">окне Размер выходного буфера, используемого для ответа.</span><span class="sxs-lookup"><span data-stu-id="359c7-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="359c7-110">заполняет Буфер, содержащий ответ.</span><span class="sxs-lookup"><span data-stu-id="359c7-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="359c7-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="359c7-111">Remarks</span></span>  
 <span data-ttu-id="359c7-112">`Request` Метод упрощает добавление неуказанных пользовательских операций.</span><span class="sxs-lookup"><span data-stu-id="359c7-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="359c7-113">Это значит, что этот метод обеспечивает расширяемость без необходимости пересмотра определения интерфейса.</span><span class="sxs-lookup"><span data-stu-id="359c7-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="359c7-114">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="359c7-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="359c7-115">Требования</span><span class="sxs-lookup"><span data-stu-id="359c7-115">Requirements</span></span>  
 <span data-ttu-id="359c7-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="359c7-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="359c7-117">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="359c7-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="359c7-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="359c7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="359c7-119">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="359c7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="359c7-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="359c7-120">See also</span></span>

- [<span data-ttu-id="359c7-121">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="359c7-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
