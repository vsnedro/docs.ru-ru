---
title: 'ICorProfilerInfo7:: Реадинмеморисимболс'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type:
- COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
ms.openlocfilehash: 6917900b7494550992dfa82f45ed0140f95e68cb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733624"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="3c51b-102">ICorProfilerInfo7:: Реадинмеморисимболс</span><span class="sxs-lookup"><span data-stu-id="3c51b-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>

<span data-ttu-id="3c51b-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="3c51b-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="3c51b-104">Считывает байты из потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="3c51b-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c51b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c51b-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c51b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3c51b-106">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="3c51b-107">окне Идентификатор модуля, содержащего поток в памяти.</span><span class="sxs-lookup"><span data-stu-id="3c51b-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="3c51b-108">окне Смещение в потоке в памяти, с которого начинается чтение байтов.</span><span class="sxs-lookup"><span data-stu-id="3c51b-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="3c51b-109">заполняет Указатель на буфер, в который будут копироваться данные.</span><span class="sxs-lookup"><span data-stu-id="3c51b-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="3c51b-110">Буфер должен иметь `countSymbolBytes` доступное место.</span><span class="sxs-lookup"><span data-stu-id="3c51b-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="3c51b-111">окне Число байтов для копирования.</span><span class="sxs-lookup"><span data-stu-id="3c51b-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="3c51b-112">заполняет При возврате из метода содержит фактическое число считанных байтов.</span><span class="sxs-lookup"><span data-stu-id="3c51b-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c51b-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3c51b-113">Return Value</span></span>  

 <span data-ttu-id="3c51b-114">`S_OK`значение, если было считано ненулевое число байтов.</span><span class="sxs-lookup"><span data-stu-id="3c51b-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="3c51b-115">`CORPROF_E_MODULE_IS_DYNAMIC`, если модуль был создан с помощью <xref:System.Reflection.Emit> .</span><span class="sxs-lookup"><span data-stu-id="3c51b-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c51b-116">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3c51b-116">Remarks</span></span>  

 <span data-ttu-id="3c51b-117">`ReadInMemorySymbols`Метод пытается выполнить чтение `countSymbolBytes` данных, начиная со смещения `symbolsReadOffset` в потоке в памяти.</span><span class="sxs-lookup"><span data-stu-id="3c51b-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="3c51b-118">Данные копируются в `pSymbolBytes` , что должно иметь `countSymbolBytes` доступное место.</span><span class="sxs-lookup"><span data-stu-id="3c51b-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="3c51b-119">`pCountSymbolsBytesRead` содержит фактическое число считанных байтов, которое может быть меньше, чем `countSymbolBytes` при достижении конца потока.</span><span class="sxs-lookup"><span data-stu-id="3c51b-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3c51b-120">Текущая реализация не поддерживает отражение. Emit.</span><span class="sxs-lookup"><span data-stu-id="3c51b-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="3c51b-121">Если модуль был создан с помощью отражения. Emit, метод возвращает значение `CORPROF_E_MODULE_IS_DYNAMIC` .</span><span class="sxs-lookup"><span data-stu-id="3c51b-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c51b-122">Требования</span><span class="sxs-lookup"><span data-stu-id="3c51b-122">Requirements</span></span>  

 <span data-ttu-id="3c51b-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c51b-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c51b-124">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3c51b-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3c51b-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c51b-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c51b-126">**.NET Framework версии:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c51b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c51b-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3c51b-127">See also</span></span>

- [<span data-ttu-id="3c51b-128">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="3c51b-128">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
