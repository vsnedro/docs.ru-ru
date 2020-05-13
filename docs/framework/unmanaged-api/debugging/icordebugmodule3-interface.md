---
title: Интерфейс ICorDebugModule3
ms.date: 03/30/2017
api_name:
- ICorDebugModule3
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3
helpviewer_keywords:
- ICorDebugModule3 interface [.NET Framework debugging]
ms.assetid: 0b69f945-263a-4e11-8512-89d27f6ea296
topic_type:
- apiref
ms.openlocfilehash: 69fd3e2df4a4eafe91cc025f28e1387cc443ea04
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212312"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="6a0f3-102">Интерфейс ICorDebugModule3</span><span class="sxs-lookup"><span data-stu-id="6a0f3-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="6a0f3-103">Создает средство чтения символов для динамического модуля.</span><span class="sxs-lookup"><span data-stu-id="6a0f3-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a0f3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a0f3-104">Syntax</span></span>  
  
```cpp  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6a0f3-105">Методы</span><span class="sxs-lookup"><span data-stu-id="6a0f3-105">Methods</span></span>  
  
|<span data-ttu-id="6a0f3-106">Метод</span><span class="sxs-lookup"><span data-stu-id="6a0f3-106">Method</span></span>|<span data-ttu-id="6a0f3-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6a0f3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6a0f3-108">Метод ICorDebugModule3::CreateReaderForInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="6a0f3-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="6a0f3-109">Создает средство чтения символов (обычно [ISymUnmanagedReader Interface](../diagnostics/isymunmanagedreader-interface.md)) для динамического модуля.</span><span class="sxs-lookup"><span data-stu-id="6a0f3-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a0f3-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="6a0f3-110">Remarks</span></span>  
 <span data-ttu-id="6a0f3-111">Этот интерфейс логически расширяет интерфейсы "ICorDebugModule" и "ICorDebugModule2".</span><span class="sxs-lookup"><span data-stu-id="6a0f3-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a0f3-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="6a0f3-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a0f3-113">Требования</span><span class="sxs-lookup"><span data-stu-id="6a0f3-113">Requirements</span></span>  
 <span data-ttu-id="6a0f3-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a0f3-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a0f3-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a0f3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a0f3-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a0f3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a0f3-117">**.NET Framework версии:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="6a0f3-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6a0f3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6a0f3-118">See also</span></span>

- [<span data-ttu-id="6a0f3-119">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="6a0f3-119">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="6a0f3-120">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="6a0f3-120">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="6a0f3-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6a0f3-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
