---
title: Метод ICLRDataTarget::SetThreadContext
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
ms.openlocfilehash: b8c4b4e585bba4df39a743273221f38ce14a9b9d
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860530"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="2fb8a-102">Метод ICLRDataTarget::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="2fb8a-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="2fb8a-103">Задает текущий контекст указанного потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="2fb8a-104">Этот метод вызывается службами доступа к данным среды CLR.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fb8a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2fb8a-105">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fb8a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2fb8a-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="2fb8a-107">окне Идентификатор операционной системы потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="2fb8a-108">окне Размер контекста.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="2fb8a-109">окне Указатель на буфер, содержащий контекст.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="2fb8a-110">Данные в `context` буфере будут иметь формат структуры Win32 `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="2fb8a-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="2fb8a-111">Контекст задает зависящие от процессора данные регистров, поэтому определение структуры Win32 `CONTEXT` зависит от архитектуры процессора.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="2fb8a-112">Описание структуры Win32 `CONTEXT` см. в файле заголовка WinNT. h.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fb8a-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="2fb8a-113">Remarks</span></span>  
 <span data-ttu-id="2fb8a-114">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fb8a-115">Требования</span><span class="sxs-lookup"><span data-stu-id="2fb8a-115">Requirements</span></span>  
 <span data-ttu-id="2fb8a-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fb8a-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fb8a-117">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="2fb8a-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2fb8a-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fb8a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fb8a-119">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fb8a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fb8a-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2fb8a-120">See also</span></span>

- [<span data-ttu-id="2fb8a-121">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="2fb8a-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
