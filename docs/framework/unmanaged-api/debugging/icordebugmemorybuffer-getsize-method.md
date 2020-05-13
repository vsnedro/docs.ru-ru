---
title: Метод ICorDebugMemoryBuffer::GetSize
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 1bef2e2d0e1a1cef74c7568fdd2e9b7986500488
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212611"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="56e9c-102">Метод ICorDebugMemoryBuffer::GetSize</span><span class="sxs-lookup"><span data-stu-id="56e9c-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="56e9c-103">Возвращает размер буфера памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="56e9c-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56e9c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56e9c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56e9c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="56e9c-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="56e9c-106">[out] Указатель на размер буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="56e9c-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56e9c-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="56e9c-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="56e9c-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="56e9c-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56e9c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="56e9c-109">Requirements</span></span>  
 <span data-ttu-id="56e9c-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56e9c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56e9c-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56e9c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56e9c-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56e9c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56e9c-113">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56e9c-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56e9c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="56e9c-114">See also</span></span>

- [<span data-ttu-id="56e9c-115">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="56e9c-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="56e9c-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="56e9c-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
