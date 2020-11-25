---
title: Метод ICLRDataTarget3::GetExceptionRecord
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6643c2af-2ee6-4789-aa25-1d8eaf500c94
topic_type:
- apiref
ms.openlocfilehash: 8f6eaa6ad310e9a01b2307bff091b670c3e1d6cb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723614"
---
# <a name="iclrdatatarget3getexceptionrecord-method"></a><span data-ttu-id="23c0a-102">Метод ICLRDataTarget3::GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="23c0a-102">ICLRDataTarget3::GetExceptionRecord Method</span></span>

<span data-ttu-id="23c0a-103">Вызывается службами доступа к данным среды CLR для извлечения записи исключения, связанной с целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="23c0a-103">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span> <span data-ttu-id="23c0a-104">Например, для целевого объекта дампа это будет эквивалентно записи исключения, передаваемой через `ExceptionParam` аргумент в функцию [Минидумпвритедумп](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) в библиотеке справки по отладке Windows (DBGHELP).</span><span class="sxs-lookup"><span data-stu-id="23c0a-104">For example, for a dump target, this would be equivalent to the exception record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23c0a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23c0a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23c0a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="23c0a-106">Parameters</span></span>  

 `bufferSize`  
 <span data-ttu-id="23c0a-107">[в] Размер входного буфера в байтах.</span><span class="sxs-lookup"><span data-stu-id="23c0a-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="23c0a-108">Оно должно быть равно `sizeof(` [MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) `)` .</span><span class="sxs-lookup"><span data-stu-id="23c0a-108">This must be equal to `sizeof(`[MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception)`)`.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="23c0a-109">[из] Указатель на тип `ULONG32`, который получает количество байтов, фактически записанных в буфер.</span><span class="sxs-lookup"><span data-stu-id="23c0a-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="23c0a-110">[из] Указатель на буфер памяти, который получает копию записи исключения.</span><span class="sxs-lookup"><span data-stu-id="23c0a-110">[out] A pointer to a memory buffer that receives a copy of the exception record.</span></span> <span data-ttu-id="23c0a-111">Запись исключения возвращается как тип [MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) .</span><span class="sxs-lookup"><span data-stu-id="23c0a-111">The exception record is returned as a [MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23c0a-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="23c0a-112">Return Value</span></span>  

 <span data-ttu-id="23c0a-113">Возвращается значение `S_OK` при успешном выполнении или код ошибки `HRESULT` при сбое.</span><span class="sxs-lookup"><span data-stu-id="23c0a-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="23c0a-114">Коды `HRESULT` могут включать значения, приведенные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="23c0a-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="23c0a-115">Код возврата</span><span class="sxs-lookup"><span data-stu-id="23c0a-115">Return code</span></span>|<span data-ttu-id="23c0a-116">Описание</span><span class="sxs-lookup"><span data-stu-id="23c0a-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="23c0a-117">Метод успешно выполнен.</span><span class="sxs-lookup"><span data-stu-id="23c0a-117">Method succeeded.</span></span> <span data-ttu-id="23c0a-118">Запись исключения скопирована в буфер вывода.</span><span class="sxs-lookup"><span data-stu-id="23c0a-118">The exception record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="23c0a-119">Нет записей исключения, связанных с целевым объектом.</span><span class="sxs-lookup"><span data-stu-id="23c0a-119">No exception record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="23c0a-120">Размер входного буфера не равен `sizeof(MINIDUMP_EXCEPTION)`.</span><span class="sxs-lookup"><span data-stu-id="23c0a-120">The input buffer size is not equal to `sizeof(MINIDUMP_EXCEPTION)`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23c0a-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="23c0a-121">Remarks</span></span>  

 <span data-ttu-id="23c0a-122">[MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) — это структура, определенная в dbghelp. h и IMAGEHLP. h в Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="23c0a-122">[MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) is a structure defined in dbghelp.h and imagehlp.h in the Windows SDK.</span></span>  
  
 <span data-ttu-id="23c0a-123">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="23c0a-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23c0a-124">Требования</span><span class="sxs-lookup"><span data-stu-id="23c0a-124">Requirements</span></span>  

 <span data-ttu-id="23c0a-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23c0a-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23c0a-126">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="23c0a-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="23c0a-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23c0a-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23c0a-128">**.NET Framework версии:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="23c0a-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23c0a-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="23c0a-129">See also</span></span>

- [<span data-ttu-id="23c0a-130">Интерфейс ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="23c0a-130">ICLRDataTarget3 Interface</span></span>](iclrdatatarget3-interface.md)
- [<span data-ttu-id="23c0a-131">Метод GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="23c0a-131">GetExceptionContextRecord Method</span></span>](iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="23c0a-132">Метод GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="23c0a-132">GetExceptionThreadID Method</span></span>](iclrdatatarget3-getexceptionthreadid-method.md)
