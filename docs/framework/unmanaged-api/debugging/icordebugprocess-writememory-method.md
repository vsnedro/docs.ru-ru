---
title: Метод ICorDebugProcess::WriteMemory
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.WriteMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type:
- apiref
ms.openlocfilehash: 0a433ccb81ef62ac92a4553a838a2c98a04fc7c1
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212819"
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="55f94-102">Метод ICorDebugProcess::WriteMemory</span><span class="sxs-lookup"><span data-stu-id="55f94-102">ICorDebugProcess::WriteMemory Method</span></span>
<span data-ttu-id="55f94-103">Записывает данные в область памяти в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="55f94-103">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55f94-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55f94-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55f94-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="55f94-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="55f94-106">окне `CORDB_ADDRESS`Значение, являющееся базовым адресом области памяти, в которую записываются данные.</span><span class="sxs-lookup"><span data-stu-id="55f94-106">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="55f94-107">Перед передачей данных система проверяет, что область памяти указанного размера, начиная с базового адреса, доступна для записи.</span><span class="sxs-lookup"><span data-stu-id="55f94-107">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="55f94-108">Если он недоступен, метод завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="55f94-108">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="55f94-109">окне Число байтов, записываемых в область памяти.</span><span class="sxs-lookup"><span data-stu-id="55f94-109">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="55f94-110">окне Буфер, содержащий записываемые данные.</span><span class="sxs-lookup"><span data-stu-id="55f94-110">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="55f94-111">заполняет Указатель на переменную, которая получает число байтов, записанных в область памяти в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="55f94-111">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="55f94-112">Если `written` аргумент имеет значение null, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="55f94-112">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55f94-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="55f94-113">Remarks</span></span>  
 <span data-ttu-id="55f94-114">Данные автоматически записываются за любые точки останова.</span><span class="sxs-lookup"><span data-stu-id="55f94-114">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="55f94-115">В .NET Framework версии 2,0 отладчики машинного кода не должны использовать этот метод для вставки точек останова в поток инструкций.</span><span class="sxs-lookup"><span data-stu-id="55f94-115">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="55f94-116">Вместо этого используйте [ICorDebugProcess2:: сетунманажедбреакпоинт](icordebugprocess2-setunmanagedbreakpoint-method.md) .</span><span class="sxs-lookup"><span data-stu-id="55f94-116">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="55f94-117">`WriteMemory`Метод следует использовать только за пределами управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="55f94-117">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="55f94-118">Этот метод может повредить среду выполнения при неправильном использовании.</span><span class="sxs-lookup"><span data-stu-id="55f94-118">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55f94-119">Требования</span><span class="sxs-lookup"><span data-stu-id="55f94-119">Requirements</span></span>  
 <span data-ttu-id="55f94-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55f94-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55f94-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55f94-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55f94-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55f94-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55f94-123">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55f94-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
