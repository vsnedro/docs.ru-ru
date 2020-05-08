---
title: Метод ICorDebugDataTarget::ReadVirtual
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
ms.openlocfilehash: 36a18d92f05db55957bba55de84490c0da1a1f86
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976516"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="1c55b-102">Метод ICorDebugDataTarget::ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="1c55b-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="1c55b-103">Возвращает блок непрерывной памяти, начиная с указанного адреса, и возвращает его в указанном буфере.</span><span class="sxs-lookup"><span data-stu-id="1c55b-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c55b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c55b-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c55b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1c55b-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="1c55b-106">окне Начальный адрес запрошенной памяти.</span><span class="sxs-lookup"><span data-stu-id="1c55b-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="1c55b-107">заполняет Буфер, в котором будет храниться память.</span><span class="sxs-lookup"><span data-stu-id="1c55b-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="1c55b-108">окне Число байтов, получаемых с целевого адреса.</span><span class="sxs-lookup"><span data-stu-id="1c55b-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="1c55b-109">заполняет Число байтов, фактически считанных из целевого адреса.</span><span class="sxs-lookup"><span data-stu-id="1c55b-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="1c55b-110">Это может быть меньше, `bytesRequested`чем.</span><span class="sxs-lookup"><span data-stu-id="1c55b-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c55b-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="1c55b-111">Remarks</span></span>  
 <span data-ttu-id="1c55b-112">Если можно считать первый байт (с указанным начальным адресом), вызов должен вернуть результат (для поддержки эффективного чтения структур данных с самоописывающей длиной, например со строками, завершающимися нулем).</span><span class="sxs-lookup"><span data-stu-id="1c55b-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c55b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="1c55b-113">Requirements</span></span>  
 <span data-ttu-id="1c55b-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c55b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c55b-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c55b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c55b-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c55b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c55b-117">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c55b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c55b-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1c55b-118">See also</span></span>

- [<span data-ttu-id="1c55b-119">Интерфейс ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="1c55b-119">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="1c55b-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1c55b-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1c55b-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="1c55b-121">Debugging</span></span>](index.md)
