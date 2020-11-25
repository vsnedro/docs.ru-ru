---
title: Метод IMetaDataAssemblyImport::FindAssembliesByName
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindAssembliesByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindAssembliesByName
helpviewer_keywords:
- FindAssembliesByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindAssembliesByName method [.NET Framework metadata]
ms.assetid: 4db97cf9-e4c1-4233-8efa-cbdc0e14a8e4
topic_type:
- apiref
ms.openlocfilehash: a2bf0335f8d75c7dbd1a651afdb54da8c7be2460
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731633"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="3c0e5-102">Метод IMetaDataAssemblyImport::FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="3c0e5-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>

<span data-ttu-id="3c0e5-103">Возвращает массив сборок с указанным `szAssemblyName` параметром, используя стандартные правила, используемые средой CLR для разрешения ссылок.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c0e5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c0e5-104">Syntax</span></span>  
  
```cpp  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,
    [in]  LPCWSTR     szPrivateBin,
    [in]  LPCWSTR     szAssemblyName,
    [out] IUnknown    *ppIUnk[],
    [in]  ULONG       cMax,
    [out] ULONG       *pcAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c0e5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3c0e5-105">Parameters</span></span>  

 `szAppBase`  
 <span data-ttu-id="3c0e5-106">окне Корневой каталог, в котором выполняется поиск данной сборки.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="3c0e5-107">Если это значение равно `null` , `FindAssembliesByName` будет искать сборку только в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="3c0e5-108">окне Список подкаталогов, разделенных точкой с запятой (например, "bin; BIN2"), в корневом каталоге, в котором выполняется поиск сборки.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="3c0e5-109">Эти каталоги проверяются в дополнение к тем, которые указаны в правилах проверки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="3c0e5-110">окне Имя искомой сборки.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="3c0e5-111">Формат этой строки определяется на странице ссылки на класс для <xref:System.Reflection.AssemblyName> .</span><span class="sxs-lookup"><span data-stu-id="3c0e5-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="3c0e5-112">окне Массив типа [IUnknown](/cpp/atl/iunknown) , в который помещаются `IMetadataAssemblyImport` указатели интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-112">[in] An array of type [IUnknown](/cpp/atl/iunknown) in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3c0e5-113">заполняет Максимальное число указателей интерфейса, которые могут быть помещены в `ppIUnk` .</span><span class="sxs-lookup"><span data-stu-id="3c0e5-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="3c0e5-114">заполняет Число возвращаемых указателей на интерфейс.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="3c0e5-115">То есть число указателей интерфейса, фактически помещаемых в `ppIUnk` .</span><span class="sxs-lookup"><span data-stu-id="3c0e5-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c0e5-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3c0e5-116">Return Value</span></span>  
  
|<span data-ttu-id="3c0e5-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c0e5-117">HRESULT</span></span>|<span data-ttu-id="3c0e5-118">Описание</span><span class="sxs-lookup"><span data-stu-id="3c0e5-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3c0e5-119">`FindAssembliesByName` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3c0e5-120">Нет сборок.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c0e5-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3c0e5-121">Remarks</span></span>  

 <span data-ttu-id="3c0e5-122">При наличии имени сборки `FindAssembliesByName` метод находит сборку, следуя стандартным правилам разрешения ссылок на сборки.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="3c0e5-123">(Дополнительные сведения см. [в разделе Обнаружение сборок в среде выполнения](../../deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` позволяет вызывающему объекту настраивать различные аспекты контекста сопоставителя сборок, такие как базовый и частный путь поиска приложения.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-123">(For more information, see [How the Runtime Locates Assemblies](../../deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="3c0e5-124">`FindAssembliesByName`Метод требует инициализации среды CLR в процессе для вызова логики разрешения сборки.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="3c0e5-125">Поэтому необходимо вызвать [CoInitialize](../hosting/coinitializeee-function.md) (передав COINITEE_DEFAULT) перед вызовом `FindAssembliesByName` , а затем выполнить вызов [каунинитиализекор](../hosting/couninitializecor-function.md).</span><span class="sxs-lookup"><span data-stu-id="3c0e5-125">Therefore, you must call [CoInitializeEE](../hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="3c0e5-126">`FindAssembliesByName` Возвращает указатель [IMetaDataImport](imetadataimport-interface.md) на файл, содержащий манифест сборки для переданного имени сборки.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-126">`FindAssembliesByName` returns an [IMetaDataImport](imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="3c0e5-127">Если заданное имя сборки не указано полностью (например, если оно не включает версию), может возвращаться несколько сборок.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="3c0e5-128">`FindAssembliesByName` обычно используется компилятором, который пытается найти ссылочную сборку во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c0e5-129">Требования</span><span class="sxs-lookup"><span data-stu-id="3c0e5-129">Requirements</span></span>  

 <span data-ttu-id="3c0e5-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c0e5-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c0e5-131">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="3c0e5-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c0e5-132">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c0e5-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c0e5-133">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c0e5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c0e5-134">См. также</span><span class="sxs-lookup"><span data-stu-id="3c0e5-134">See also</span></span>

- [<span data-ttu-id="3c0e5-135">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="3c0e5-135">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="3c0e5-136">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="3c0e5-136">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
