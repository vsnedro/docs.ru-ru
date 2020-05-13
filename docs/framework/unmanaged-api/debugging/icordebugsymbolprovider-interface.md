---
title: Интерфейс ICorDebugSymbolProvider
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
ms.openlocfilehash: 25faad4f4bc67b57c339bc63d1a18ab4d275cd71
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379341"
---
# <a name="icordebugsymbolprovider-interface"></a><span data-ttu-id="81624-102">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="81624-102">ICorDebugSymbolProvider Interface</span></span>
<span data-ttu-id="81624-103">Предоставляет методы, которые могут использоваться для получения сведений об отладочных символах.</span><span class="sxs-lookup"><span data-stu-id="81624-103">Provides methods that can be used to retrieve debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="81624-104">Методы</span><span class="sxs-lookup"><span data-stu-id="81624-104">Methods</span></span>  
  
|<span data-ttu-id="81624-105">Метод</span><span class="sxs-lookup"><span data-stu-id="81624-105">Method</span></span>|<span data-ttu-id="81624-106">Описание</span><span class="sxs-lookup"><span data-stu-id="81624-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="81624-107">Метод GetAssemblyImageBytes</span><span class="sxs-lookup"><span data-stu-id="81624-107">GetAssemblyImageBytes Method</span></span>](icordebugsymbolprovider-getassemblyimagebytes-method.md)|<span data-ttu-id="81624-108">Считывает данные из объединенной сборки для указанного относительного виртуального адреса (RVA) в объединенной сборке.</span><span class="sxs-lookup"><span data-stu-id="81624-108">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>|  
|[<span data-ttu-id="81624-109">Метод GetAssemblyImageMetadata</span><span class="sxs-lookup"><span data-stu-id="81624-109">GetAssemblyImageMetadata Method</span></span>](icordebugsymbolprovider-getassemblyimagemetadata-method.md)|<span data-ttu-id="81624-110">Возвращает метаданные из объединенной сборки.</span><span class="sxs-lookup"><span data-stu-id="81624-110">Returns the metadata from a merged assembly.</span></span>|  
|[<span data-ttu-id="81624-111">Метод GetCodeRange</span><span class="sxs-lookup"><span data-stu-id="81624-111">GetCodeRange Method</span></span>](icordebugsymbolprovider-getcoderange-method.md)|<span data-ttu-id="81624-112">Получает начальный адрес метода и размер для указанного относительного виртуального адреса (RVA) в методе.</span><span class="sxs-lookup"><span data-stu-id="81624-112">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>|  
|[<span data-ttu-id="81624-113">Метод GetInstanceFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="81624-113">GetInstanceFieldSymbols Method</span></span>](icordebugsymbolprovider-getinstancefieldsymbols-method.md)|<span data-ttu-id="81624-114">Получает символы поля экземпляра, которые соответствуют сигнатуре TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="81624-114">Gets the instance field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="81624-115">Метод GetMergedAssemblyRecords</span><span class="sxs-lookup"><span data-stu-id="81624-115">GetMergedAssemblyRecords Method</span></span>](icordebugsymbolprovider-getmergedassemblyrecords-method.md)|<span data-ttu-id="81624-116">Возвращает символьные записи для всех объединенных сборок.</span><span class="sxs-lookup"><span data-stu-id="81624-116">Gets the symbol records for all the merged assemblies.</span></span>|  
|[<span data-ttu-id="81624-117">Метод GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="81624-117">GetMethodLocalSymbols Method</span></span>](icordebugsymbolprovider-getmethodlocalsymbols-method.md)|<span data-ttu-id="81624-118">Получает локальные символы метода с учетом относительного виртуального адреса (RVA) этого метода.</span><span class="sxs-lookup"><span data-stu-id="81624-118">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="81624-119">Метод GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="81624-119">GetMethodParameterSymbols Method</span></span>](icordebugsymbolprovider-getmethodparametersymbols-method.md)|<span data-ttu-id="81624-120">Получает символы параметров метода для указанного относительного виртуального адреса (RVA) этого метода.</span><span class="sxs-lookup"><span data-stu-id="81624-120">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="81624-121">Метод GetMethodProps</span><span class="sxs-lookup"><span data-stu-id="81624-121">GetMethodProps Method</span></span>](icordebugsymbolprovider-getmethodprops-method.md)|<span data-ttu-id="81624-122">Возвращает сведения о свойствах метода, такие как токен метаданных метода и сведения о его универсальных параметрах, для указанного относительного виртуального адреса (RVA) в этом методе.</span><span class="sxs-lookup"><span data-stu-id="81624-122">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>|  
|[<span data-ttu-id="81624-123">Метод GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="81624-123">GetObjectSize Method</span></span>](icordebugsymbolprovider-getobjectsize-method.md)|<span data-ttu-id="81624-124">Возвращает размер объекта для объекта на основе его сигнатуры TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="81624-124">Returns the object size for an object based on its typespec signature.</span></span>|  
|[<span data-ttu-id="81624-125">Метод GetStaticFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="81624-125">GetStaticFieldSymbols Method</span></span>](icordebugsymbolprovider-getstaticfieldsymbols-method.md)|<span data-ttu-id="81624-126">Получает символы статического поля, которые соответствуют сигнатуре TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="81624-126">Gets the static field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="81624-127">Метод GetTypeProps</span><span class="sxs-lookup"><span data-stu-id="81624-127">GetTypeProps Method</span></span>](icordebugsymbolprovider-gettypeprops-method.md)|<span data-ttu-id="81624-128">Возвращает сведения о свойствах типа, такие как число сигнатур его универсальных параметров, для указанного относительного виртуального адреса (RVA) в таблице VTable.</span><span class="sxs-lookup"><span data-stu-id="81624-128">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81624-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="81624-129">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="81624-130">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="81624-130">This interface is available with .NET Native only.</span></span> <span data-ttu-id="81624-131">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="81624-131">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81624-132">Требования</span><span class="sxs-lookup"><span data-stu-id="81624-132">Requirements</span></span>  
 <span data-ttu-id="81624-133">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81624-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81624-134">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81624-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81624-135">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81624-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81624-136">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81624-136">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81624-137">См. также</span><span class="sxs-lookup"><span data-stu-id="81624-137">See also</span></span>

- [<span data-ttu-id="81624-138">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="81624-138">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="81624-139">Отладка</span><span class="sxs-lookup"><span data-stu-id="81624-139">Debugging</span></span>](index.md)
