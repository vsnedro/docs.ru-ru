---
title: Метод ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
ms.openlocfilehash: 1e040453d5eb7a312f2e665974486492b99de16d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719688"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="27e18-102">Метод ICorDebugAssembly3::EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="27e18-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>

<span data-ttu-id="27e18-103">Получает перечислитель для сборок, содержащихся в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="27e18-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27e18-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27e18-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27e18-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="27e18-105">Parameters</span></span>  

 `ppAssemblies`  
 <span data-ttu-id="27e18-106">[выходной] Указатель на адрес объекта интерфейса ICorDebugAssemblyEnum, который является перечислителем.</span><span class="sxs-lookup"><span data-stu-id="27e18-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27e18-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="27e18-107">Return Value</span></span>  

 <span data-ttu-id="27e18-108">`S_OK`, если этот объект `ICorDebugAssembly3` является контейнером; в противном случае — `S_FALSE`, и перечисление будет пустым.</span><span class="sxs-lookup"><span data-stu-id="27e18-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27e18-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="27e18-109">Remarks</span></span>  

 <span data-ttu-id="27e18-110">Символы необходимы для перечисления вложенных сборок.</span><span class="sxs-lookup"><span data-stu-id="27e18-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="27e18-111">Если они отсутствуют, метод возвращает `S_FALSE`, и действительный перечислитель отсутствует.</span><span class="sxs-lookup"><span data-stu-id="27e18-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27e18-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="27e18-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27e18-113">Требования</span><span class="sxs-lookup"><span data-stu-id="27e18-113">Requirements</span></span>  

 <span data-ttu-id="27e18-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27e18-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27e18-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27e18-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27e18-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27e18-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27e18-117">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27e18-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27e18-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="27e18-118">See also</span></span>

- [<span data-ttu-id="27e18-119">Интерфейс ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="27e18-119">ICorDebugAssembly3 Interface</span></span>](icordebugassembly3-interface.md)
- [<span data-ttu-id="27e18-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="27e18-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
