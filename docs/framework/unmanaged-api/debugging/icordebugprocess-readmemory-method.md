---
title: Метод ICorDebugProcess::ReadMemory
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
ms.openlocfilehash: a0abc7168ff7bffdbb835c1c1bc93de9df6e381c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694871"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="09905-102">Метод ICorDebugProcess::ReadMemory</span><span class="sxs-lookup"><span data-stu-id="09905-102">ICorDebugProcess::ReadMemory Method</span></span>

<span data-ttu-id="09905-103">Считывает указанную область памяти для этого процесса.</span><span class="sxs-lookup"><span data-stu-id="09905-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09905-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09905-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09905-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="09905-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="09905-106">окне `CORDB_ADDRESS` Значение типа, указывающее базовый адрес памяти для чтения.</span><span class="sxs-lookup"><span data-stu-id="09905-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="09905-107">окне Число байтов, считываемых из памяти.</span><span class="sxs-lookup"><span data-stu-id="09905-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="09905-108">заполняет Буфер, который получает содержимое памяти.</span><span class="sxs-lookup"><span data-stu-id="09905-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="09905-109">заполняет Указатель на число байтов, передаваемых в указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="09905-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09905-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="09905-110">Remarks</span></span>  

 <span data-ttu-id="09905-111">`ReadMemory`Метод в основном предназначен для использования в отладке взаимодействия для проверки областей памяти, используемых неуправляемой частью отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="09905-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="09905-112">Этот метод также можно использовать для считывания кода на языке MSIL и собственного JIT-скомпилированного кода.</span><span class="sxs-lookup"><span data-stu-id="09905-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="09905-113">Все управляемые точки останова будут удалены из данных, возвращаемых в `buffer` параметре.</span><span class="sxs-lookup"><span data-stu-id="09905-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="09905-114">Никакие изменения для собственных точек останова, заданных [ICorDebugProcess2:: сетунманажедбреакпоинт](icordebugprocess2-setunmanagedbreakpoint-method.md), не выполняются.</span><span class="sxs-lookup"><span data-stu-id="09905-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="09905-115">Кэширование памяти процесса не выполняется.</span><span class="sxs-lookup"><span data-stu-id="09905-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09905-116">Требования</span><span class="sxs-lookup"><span data-stu-id="09905-116">Requirements</span></span>  

 <span data-ttu-id="09905-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09905-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09905-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09905-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09905-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09905-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09905-120">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09905-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
