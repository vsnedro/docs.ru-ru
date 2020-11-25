---
title: Метод ICorDebugMemoryBuffer::GetSize
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 7f5458dd12ca83c1a5190bbf7fab0f8e5d06a0e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710767"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="7f208-102">Метод ICorDebugMemoryBuffer::GetSize</span><span class="sxs-lookup"><span data-stu-id="7f208-102">ICorDebugMemoryBuffer::GetSize Method</span></span>

<span data-ttu-id="7f208-103">Возвращает размер буфера памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="7f208-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f208-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f208-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f208-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7f208-105">Parameters</span></span>  

 `pcbBufferLength`  
 <span data-ttu-id="7f208-106">[out] Указатель на размер буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="7f208-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f208-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="7f208-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7f208-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="7f208-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f208-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7f208-109">Requirements</span></span>  

 <span data-ttu-id="7f208-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f208-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f208-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f208-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f208-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f208-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f208-113">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f208-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f208-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7f208-114">See also</span></span>

- [<span data-ttu-id="7f208-115">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="7f208-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="7f208-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7f208-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
