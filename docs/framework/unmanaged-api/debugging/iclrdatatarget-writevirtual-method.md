---
title: Метод ICLRDataTarget::WriteVirtual
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.WriteVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::WriteVirtual
helpviewer_keywords:
- ICLRDataTarget::WriteVirtual method [.NET Framework debugging]
- WriteVirtual method [.NET Framework debugging]
ms.assetid: d627e8b7-a605-40ac-b9bb-da9a3f1b66d9
topic_type:
- apiref
ms.openlocfilehash: 6a7a7736837f7e6bbf1ad4982e78a75550abbeab
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860503"
---
# <a name="iclrdatatargetwritevirtual-method"></a><span data-ttu-id="32a37-102">Метод ICLRDataTarget::WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="32a37-102">ICLRDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="32a37-103">Записывает данные из указанного буфера в указанный адрес виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="32a37-103">Writes data from the specified buffer to the specified virtual memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32a37-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32a37-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32a37-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="32a37-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="32a37-106">окне CLRDATA_ADDRESS, в которой хранится адрес виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="32a37-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="32a37-107">окне Указатель на буфер, в котором хранятся записываемые данные.</span><span class="sxs-lookup"><span data-stu-id="32a37-107">[in] A pointer to a buffer that stores the data to be written.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="32a37-108">окне Число записываемых байтов.</span><span class="sxs-lookup"><span data-stu-id="32a37-108">[in] The number of bytes to be written.</span></span>  
  
 `bytesWritten`  
 <span data-ttu-id="32a37-109">заполняет Указатель на фактическое число записанных байтов.</span><span class="sxs-lookup"><span data-stu-id="32a37-109">[out] A pointer to the actual number of bytes that were written.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32a37-110">Требования</span><span class="sxs-lookup"><span data-stu-id="32a37-110">Requirements</span></span>  
 <span data-ttu-id="32a37-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32a37-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32a37-112">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="32a37-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="32a37-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32a37-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32a37-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32a37-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32a37-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="32a37-115">See also</span></span>

- [<span data-ttu-id="32a37-116">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="32a37-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
