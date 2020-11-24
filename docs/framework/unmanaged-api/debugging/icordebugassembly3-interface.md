---
title: Интерфейс ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
ms.openlocfilehash: 0260267a05a880fbb3ac48325e55deff326f5f87
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688371"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="0ca2b-102">Интерфейс ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="0ca2b-102">ICorDebugAssembly3 Interface</span></span>

<span data-ttu-id="0ca2b-103">Логически расширяет интерфейс ICorDebugAssembly для обеспечения поддержки контейнерных сборок и их вложенных сборок.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ca2b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0ca2b-104">Methods</span></span>  
  
|<span data-ttu-id="0ca2b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0ca2b-105">Method</span></span>|<span data-ttu-id="0ca2b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0ca2b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ca2b-107">Метод EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="0ca2b-107">EnumerateContainedAssemblies Method</span></span>](icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="0ca2b-108">Получает перечислитель для сборок, содержащихся в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="0ca2b-109">Метод GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="0ca2b-109">GetContainerAssembly Method</span></span>](icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="0ca2b-110">Возвращает контейнерную сборку этого объекта `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ca2b-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0ca2b-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ca2b-112">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="0ca2b-113">Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ca2b-114">Требования</span><span class="sxs-lookup"><span data-stu-id="0ca2b-114">Requirements</span></span>  

 <span data-ttu-id="0ca2b-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ca2b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ca2b-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ca2b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ca2b-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ca2b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ca2b-118">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ca2b-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ca2b-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0ca2b-119">See also</span></span>

- [<span data-ttu-id="0ca2b-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0ca2b-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0ca2b-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="0ca2b-121">Debugging</span></span>](index.md)
