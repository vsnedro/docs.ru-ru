---
title: Метод IHostAssemblyStore::ProvideAssembly
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type:
- apiref
ms.openlocfilehash: 162def0d703ea81efc3df3ea5ee08b58e34822e6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501577"
---
# <a name="ihostassemblystoreprovideassembly-method"></a><span data-ttu-id="b138e-102">Метод IHostAssemblyStore::ProvideAssembly</span><span class="sxs-lookup"><span data-stu-id="b138e-102">IHostAssemblyStore::ProvideAssembly Method</span></span>
<span data-ttu-id="b138e-103">Возвращает ссылку на сборку, на которую не ссылается [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) , возвращаемую из [IHostAssemblyManager:: GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="b138e-103">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that is returned from [IHostAssemblyManager::GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span> <span data-ttu-id="b138e-104">Среда CLR вызывает `ProvideAssembly` для каждой сборки, которая не отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="b138e-104">The common language runtime (CLR) calls `ProvideAssembly` for each assembly that does not appear in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b138e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b138e-105">Syntax</span></span>  
  
```cpp  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b138e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b138e-106">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="b138e-107">окне Указатель на экземпляр [ассемблибиндинфо](assemblybindinfo-structure.md) , используемый узлом для определения определенных характеристик привязки, включая присутствие или отсутствие политики управления версиями, а также сборку, к которой необходимо выполнить привязку.</span><span class="sxs-lookup"><span data-stu-id="b138e-107">[in] A pointer to an [AssemblyBindInfo](assemblybindinfo-structure.md) instance that the host uses to determine certain bind characteristics, including the presence or absence of any versioning policy, and which assembly to bind to.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="b138e-108">заполняет Указатель на уникальный идентификатор для запрошенной сборки для этого `IStream` .</span><span class="sxs-lookup"><span data-stu-id="b138e-108">[out] A pointer to a unique identifier for the requested assembly for this `IStream`.</span></span>  
  
 `pHostContext`  
 <span data-ttu-id="b138e-109">заполняет Указатель на данные конкретного узла, который используется для определения свидетельства запрошенной сборки без вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="b138e-109">[out] A pointer to host-specific data that is used to determine the evidence of the requested assembly without the need of a platform invoke call.</span></span> <span data-ttu-id="b138e-110">`pHostContext`соответствует <xref:System.Reflection.Assembly.HostContext%2A> свойству управляемого <xref:System.Reflection.Assembly> класса.</span><span class="sxs-lookup"><span data-stu-id="b138e-110">`pHostContext` corresponds to the <xref:System.Reflection.Assembly.HostContext%2A> property of the managed <xref:System.Reflection.Assembly> class.</span></span>  
  
 `ppStmAssemblyImage`  
 <span data-ttu-id="b138e-111">заполняет Указатель на адрес объекта `IStream` , который содержит загружаемый переносимый исполняемый файл (PE), или значение null, если сборку найти не удалось.</span><span class="sxs-lookup"><span data-stu-id="b138e-111">[out] A pointer to the address of an `IStream` that contains the portable executable (PE) image to be loaded, or null if the assembly could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="b138e-112">заполняет Указатель на адрес `IStream` , содержащий сведения об отладке программы (PDB), или значение null, если PDB-файл не найден.</span><span class="sxs-lookup"><span data-stu-id="b138e-112">[out] A pointer to the address of an `IStream` that contains the program debug (PDB) information, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b138e-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b138e-113">Return Value</span></span>  
  
|<span data-ttu-id="b138e-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b138e-114">HRESULT</span></span>|<span data-ttu-id="b138e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b138e-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b138e-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="b138e-116">S_OK</span></span>|<span data-ttu-id="b138e-117">`ProvideAssembly`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="b138e-117">`ProvideAssembly` returned successfully.</span></span>|  
|<span data-ttu-id="b138e-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b138e-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b138e-119">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b138e-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b138e-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b138e-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b138e-121">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="b138e-121">The call timed out.</span></span>|  
|<span data-ttu-id="b138e-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b138e-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b138e-123">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="b138e-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b138e-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b138e-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b138e-125">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="b138e-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b138e-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b138e-126">E_FAIL</span></span>|<span data-ttu-id="b138e-127">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="b138e-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b138e-128">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b138e-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b138e-129">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b138e-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b138e-130">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="b138e-130">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="b138e-131">Не удалось найти запрошенную сборку.</span><span class="sxs-lookup"><span data-stu-id="b138e-131">The requested assembly could not be located.</span></span>|  
|<span data-ttu-id="b138e-132">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="b138e-132">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="b138e-133">Размер буфера, указанный в, `pAssemblyId` недостаточно велик для хранения идентификатора, который требуется вернуть узлу.</span><span class="sxs-lookup"><span data-stu-id="b138e-133">The buffer size specified by `pAssemblyId` is not large enough to hold the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b138e-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="b138e-134">Remarks</span></span>  
 <span data-ttu-id="b138e-135">Значение идентификатора, возвращенное для `pAssemblyId` , задается узлом.</span><span class="sxs-lookup"><span data-stu-id="b138e-135">The identity value returned for `pAssemblyId` is specified by the host.</span></span> <span data-ttu-id="b138e-136">Идентификаторы должны быть уникальными в течение всего времени существования процесса.</span><span class="sxs-lookup"><span data-stu-id="b138e-136">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="b138e-137">Среда CLR использует это значение в качестве уникального идентификатора потока.</span><span class="sxs-lookup"><span data-stu-id="b138e-137">The CLR uses this value as a unique identifier for the stream.</span></span> <span data-ttu-id="b138e-138">Он проверяет каждое значение по значениям `pAssemblyId` , возвращаемым другими вызовами метода `ProvideAssembly` .</span><span class="sxs-lookup"><span data-stu-id="b138e-138">It checks each value against the values for `pAssemblyId` returned by other calls to `ProvideAssembly`.</span></span> <span data-ttu-id="b138e-139">Если узел возвращает одно и то же `pAssemblyId` значение для другого `IStream` , среда CLR проверяет, было ли уже сопоставлено содержимое этого потока.</span><span class="sxs-lookup"><span data-stu-id="b138e-139">If the host returns the same `pAssemblyId` value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="b138e-140">Если это так, среда выполнения загружает существующую копию изображения вместо сопоставления нового.</span><span class="sxs-lookup"><span data-stu-id="b138e-140">If so, the runtime loads the existing copy of the image instead of mapping a new one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b138e-141">Требования</span><span class="sxs-lookup"><span data-stu-id="b138e-141">Requirements</span></span>  
 <span data-ttu-id="b138e-142">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b138e-142">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b138e-143">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b138e-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b138e-144">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b138e-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b138e-145">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b138e-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b138e-146">См. также</span><span class="sxs-lookup"><span data-stu-id="b138e-146">See also</span></span>

- [<span data-ttu-id="b138e-147">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="b138e-147">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="b138e-148">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="b138e-148">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="b138e-149">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="b138e-149">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
