---
title: Метод ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 51e68e73983425cdd7d648b6856809fcba590f70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688553"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="9d3f2-102">Метод ICorDebugAssembly3::GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="9d3f2-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>

<span data-ttu-id="9d3f2-103">Возвращает контейнерную сборку этого объекта `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="9d3f2-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d3f2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d3f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d3f2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9d3f2-105">Parameters</span></span>  

 `ppAssembly`  
 <span data-ttu-id="9d3f2-106">Указатель на адрес объекта ICorDebugAssembly, который представляет сборку контейнера, или **значение NULL** , если вызов метода завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="9d3f2-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d3f2-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9d3f2-107">Return Value</span></span>  

 <span data-ttu-id="9d3f2-108">`S_OK` значение, если вызов метода выполнен. в противном случае, `S_FALSE` и `ppAssembly` имеет **значение NULL**.</span><span class="sxs-lookup"><span data-stu-id="9d3f2-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d3f2-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9d3f2-109">Remarks</span></span>  

 <span data-ttu-id="9d3f2-110">Если эта сборка была объединена с другими сборками внутри одиночной контейнерной сборки, этот метод возвращает контейнерную сборку.</span><span class="sxs-lookup"><span data-stu-id="9d3f2-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="9d3f2-111">Дополнительные сведения и терминология см. в разделе [ICorDebugProcess6:: EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9d3f2-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d3f2-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="9d3f2-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d3f2-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9d3f2-113">Requirements</span></span>  

 <span data-ttu-id="9d3f2-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d3f2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d3f2-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d3f2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d3f2-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d3f2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d3f2-117">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d3f2-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d3f2-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9d3f2-118">See also</span></span>

- [<span data-ttu-id="9d3f2-119">Интерфейс ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="9d3f2-119">ICorDebugAssembly3 Interface</span></span>](icordebugassembly3-interface.md)
- [<span data-ttu-id="9d3f2-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9d3f2-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
