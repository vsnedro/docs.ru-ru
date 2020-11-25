---
title: Метод ICorDebugMutableDataTarget::WriteVirtual
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
ms.openlocfilehash: 453ab23e292c5eab4a8300c32bf76743b787750d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709340"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="81196-102">Метод ICorDebugMutableDataTarget::WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="81196-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>

<span data-ttu-id="81196-103">Записывает память в адресное пространство целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="81196-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81196-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81196-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81196-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="81196-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="81196-106">[in] Адрес для записи содержимого `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="81196-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="81196-107">[в] Указатель на массив байтов, содержащий байты для записи.</span><span class="sxs-lookup"><span data-stu-id="81196-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="81196-108">[in] Количество байтов в `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="81196-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81196-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="81196-109">Return Value</span></span>  

 <span data-ttu-id="81196-110">Значение `S_OK` при успешном выполнении или любое другое значение `HRESULT` в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="81196-110">`S_OK` on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81196-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="81196-111">Remarks</span></span>  

 <span data-ttu-id="81196-112">Если не удается записать все байты, вызов метода завершается ошибкой без изменения каких-либо байтов в целевом адресном пространстве.</span><span class="sxs-lookup"><span data-stu-id="81196-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="81196-113">(В противном случае целевое адресное пространство оказалось бы в несогласованном состоянии, что сделало бы ненадежной дальнейшую отладку.)</span><span class="sxs-lookup"><span data-stu-id="81196-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81196-114">Требования</span><span class="sxs-lookup"><span data-stu-id="81196-114">Requirements</span></span>  

 <span data-ttu-id="81196-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81196-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81196-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81196-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81196-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81196-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81196-118">**.NET Framework версии:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81196-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81196-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="81196-119">See also</span></span>

- [<span data-ttu-id="81196-120">Интерфейс ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="81196-120">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="81196-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="81196-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
