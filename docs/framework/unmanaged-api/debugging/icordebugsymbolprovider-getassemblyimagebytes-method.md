---
title: Метод ICorDebugSymbolProvider::GetAssemblyImageBytes
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
ms.openlocfilehash: b52614065d599edf8e556524c33e8bc50b4924ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709184"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="d052b-102">Метод ICorDebugSymbolProvider::GetAssemblyImageBytes</span><span class="sxs-lookup"><span data-stu-id="d052b-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>

<span data-ttu-id="d052b-103">Считывает данные из объединенной сборки для указанного относительного виртуального адреса (RVA) в объединенной сборке.</span><span class="sxs-lookup"><span data-stu-id="d052b-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d052b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d052b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,
   [in] ULONG32 length,
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d052b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d052b-105">Parameters</span></span>  

 `rva`  
 <span data-ttu-id="d052b-106">[in] Относительный виртуальный адрес (RVA) в объединенной сборке.</span><span class="sxs-lookup"><span data-stu-id="d052b-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="d052b-107">Число байт для чтения из объединенной сборки.</span><span class="sxs-lookup"><span data-stu-id="d052b-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="d052b-108">Указатель на адрес объекта [икордебугмеморибуффер](icordebugmemorybuffer-interface.md) , который содержит сведения о буфере памяти с объединенными метаданными сборки.</span><span class="sxs-lookup"><span data-stu-id="d052b-108">A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d052b-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d052b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d052b-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="d052b-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d052b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d052b-111">Requirements</span></span>  

 <span data-ttu-id="d052b-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d052b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d052b-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d052b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d052b-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d052b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d052b-115">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d052b-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d052b-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d052b-116">See also</span></span>

- [<span data-ttu-id="d052b-117">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="d052b-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="d052b-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d052b-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
