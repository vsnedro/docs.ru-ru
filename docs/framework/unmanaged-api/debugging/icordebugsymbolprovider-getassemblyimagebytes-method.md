---
title: Метод ICorDebugSymbolProvider::GetAssemblyImageBytes
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
ms.openlocfilehash: a555acb9e23098b0a0f70924032771b1ae18e88e
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83376118"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="3e235-102">Метод ICorDebugSymbolProvider::GetAssemblyImageBytes</span><span class="sxs-lookup"><span data-stu-id="3e235-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>
<span data-ttu-id="3e235-103">Считывает данные из объединенной сборки для указанного относительного виртуального адреса (RVA) в объединенной сборке.</span><span class="sxs-lookup"><span data-stu-id="3e235-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e235-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e235-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,
   [in] ULONG32 length,
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e235-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3e235-105">Parameters</span></span>  
 `rva`  
 <span data-ttu-id="3e235-106">[in] Относительный виртуальный адрес (RVA) в объединенной сборке.</span><span class="sxs-lookup"><span data-stu-id="3e235-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="3e235-107">Число байт для чтения из объединенной сборки.</span><span class="sxs-lookup"><span data-stu-id="3e235-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="3e235-108">Указатель на адрес объекта [икордебугмеморибуффер](icordebugmemorybuffer-interface.md) , который содержит сведения о буфере памяти с объединенными метаданными сборки.</span><span class="sxs-lookup"><span data-stu-id="3e235-108">A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e235-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="3e235-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3e235-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="3e235-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e235-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3e235-111">Requirements</span></span>  
 <span data-ttu-id="3e235-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e235-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e235-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e235-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e235-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e235-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e235-115">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e235-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e235-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3e235-116">See also</span></span>

- [<span data-ttu-id="3e235-117">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="3e235-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="3e235-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3e235-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
