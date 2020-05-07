---
title: Метод ICLRDataTarget::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
ms.openlocfilehash: 5c0fb023dd355f3a9c1ed846913f86b354592ed5
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860606"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="ec480-102">Метод ICLRDataTarget::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="ec480-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="ec480-103">Возвращает текущий контекст выполнения для данного потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="ec480-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="ec480-104">Этот метод вызывается службами доступа к данным среды CLR.</span><span class="sxs-lookup"><span data-stu-id="ec480-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec480-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec480-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec480-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ec480-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="ec480-107">окне Идентификатор операционной системы потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="ec480-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="ec480-108">окне Флаги, указывающие, какие части контекста должны быть возвращены.</span><span class="sxs-lookup"><span data-stu-id="ec480-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="ec480-109">Реализация возвратит по крайней мере эти части контекста.</span><span class="sxs-lookup"><span data-stu-id="ec480-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="ec480-110">окне Размер контекста.</span><span class="sxs-lookup"><span data-stu-id="ec480-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="ec480-111">заполняет Указатель на буфер, в который будет помещен контекст.</span><span class="sxs-lookup"><span data-stu-id="ec480-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="ec480-112">Данные в `context` буфере должны быть в формате структуры Win32 `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="ec480-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="ec480-113">Контекст задает зависящие от процессора данные регистров, поэтому определение структуры Win32 `CONTEXT` зависит от архитектуры процессора.</span><span class="sxs-lookup"><span data-stu-id="ec480-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="ec480-114">Описание структуры Win32 `CONTEXT` см. в файле заголовка WinNT. h.</span><span class="sxs-lookup"><span data-stu-id="ec480-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec480-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="ec480-115">Remarks</span></span>  
 <span data-ttu-id="ec480-116">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="ec480-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec480-117">Требования</span><span class="sxs-lookup"><span data-stu-id="ec480-117">Requirements</span></span>  
 <span data-ttu-id="ec480-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec480-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec480-119">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="ec480-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="ec480-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec480-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec480-121">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec480-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec480-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ec480-122">See also</span></span>

- [<span data-ttu-id="ec480-123">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="ec480-123">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
