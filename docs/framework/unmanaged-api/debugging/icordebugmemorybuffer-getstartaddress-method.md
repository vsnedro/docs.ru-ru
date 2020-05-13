---
title: Метод ICorDebugMemoryBuffer::GetStartAddress
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: 47369c744ee42fb03857a3e69063a04e4f509d0d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212351"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="47d54-102">Метод ICorDebugMemoryBuffer::GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="47d54-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="47d54-103">Возвращает начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="47d54-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47d54-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47d54-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47d54-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="47d54-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="47d54-106">[out] Указатель на начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="47d54-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47d54-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="47d54-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="47d54-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="47d54-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47d54-109">Требования</span><span class="sxs-lookup"><span data-stu-id="47d54-109">Requirements</span></span>  
 <span data-ttu-id="47d54-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47d54-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47d54-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47d54-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47d54-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47d54-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47d54-113">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47d54-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47d54-114">См. также</span><span class="sxs-lookup"><span data-stu-id="47d54-114">See also</span></span>

- [<span data-ttu-id="47d54-115">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="47d54-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="47d54-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="47d54-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
