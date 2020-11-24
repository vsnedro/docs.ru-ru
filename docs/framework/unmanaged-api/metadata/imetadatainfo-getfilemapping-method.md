---
title: Метод IMetaDataInfo::GetFileMapping
ms.date: 03/30/2017
api_name:
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
ms.openlocfilehash: 8823f3cc016072d3f20100c29532459da5e97492
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682395"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="55c47-102">Метод IMetaDataInfo::GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="55c47-102">IMetaDataInfo::GetFileMapping Method</span></span>

<span data-ttu-id="55c47-103">Возвращает область памяти сопоставленного файла и тип сопоставления.</span><span class="sxs-lookup"><span data-stu-id="55c47-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55c47-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55c47-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,
    [out] ULONGLONG            *pcbData,
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55c47-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="55c47-105">Parameters</span></span>  

 `ppvData`  
 <span data-ttu-id="55c47-106">заполняет Указатель на начало сопоставленного файла.</span><span class="sxs-lookup"><span data-stu-id="55c47-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="55c47-107">заполняет Размер сопоставленной области.</span><span class="sxs-lookup"><span data-stu-id="55c47-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="55c47-108">Если `pdwMappingType` имеет значение `fmFlat` , то это размер файла.</span><span class="sxs-lookup"><span data-stu-id="55c47-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="55c47-109">заполняет Значение [CorFileMapping](corfilemapping-enumeration.md) , указывающее тип сопоставления.</span><span class="sxs-lookup"><span data-stu-id="55c47-109">[out] A [CorFileMapping](corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="55c47-110">Текущая реализация среды CLR всегда возвращает `fmFlat` .</span><span class="sxs-lookup"><span data-stu-id="55c47-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="55c47-111">Другие значения зарезервированы для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="55c47-111">Other values are reserved for future use.</span></span> <span data-ttu-id="55c47-112">Однако всегда следует проверять возвращаемое значение, так как в будущих версиях или выпусках служб могут быть включены другие значения.</span><span class="sxs-lookup"><span data-stu-id="55c47-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55c47-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="55c47-113">Return Value</span></span>  
  
|<span data-ttu-id="55c47-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="55c47-114">HRESULT</span></span>|<span data-ttu-id="55c47-115">Описание</span><span class="sxs-lookup"><span data-stu-id="55c47-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="55c47-116">Все выходные данные заполнены.</span><span class="sxs-lookup"><span data-stu-id="55c47-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="55c47-117">Значение NULL передано в качестве значения аргумента.</span><span class="sxs-lookup"><span data-stu-id="55c47-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="55c47-118">Реализация CLR не может предоставить сведения о области памяти.</span><span class="sxs-lookup"><span data-stu-id="55c47-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="55c47-119">Это может происходить по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="55c47-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="55c47-120">— Область метаданных была открыта с помощью `ofWrite` `ofCopyMemory` флага или.</span><span class="sxs-lookup"><span data-stu-id="55c47-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="55c47-121">— Область метаданных была открыта без `ofReadOnly` флага.</span><span class="sxs-lookup"><span data-stu-id="55c47-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="55c47-122">— Метод [IMetaDataDispenser:: OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) использовался для открытия только части файла с метаданными.</span><span class="sxs-lookup"><span data-stu-id="55c47-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="55c47-123">— Файл не является переносимым исполняемым файлом (PE).</span><span class="sxs-lookup"><span data-stu-id="55c47-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="55c47-124">**Примечание.**  Эти условия зависят от реализации CLR и, скорее всего, будут ослаблены в будущих версиях среды CLR.</span><span class="sxs-lookup"><span data-stu-id="55c47-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55c47-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="55c47-125">Remarks</span></span>  

 <span data-ttu-id="55c47-126">Память, `ppvData` на которую указывает указатель, допустима, только если базовая область метаданных открыта.</span><span class="sxs-lookup"><span data-stu-id="55c47-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="55c47-127">Чтобы этот метод работал, при сопоставлении метаданных файла на диске с памятью путем вызова метода [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) необходимо указать `ofReadOnly` флаг и не указывать `ofWrite` `ofCopyMemory` флаг или.</span><span class="sxs-lookup"><span data-stu-id="55c47-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="55c47-128">Выбранный тип сопоставления файлов для каждой области зависит от конкретной реализации среды CLR.</span><span class="sxs-lookup"><span data-stu-id="55c47-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="55c47-129">Он не может быть задан пользователем.</span><span class="sxs-lookup"><span data-stu-id="55c47-129">It cannot be set by the user.</span></span> <span data-ttu-id="55c47-130">Текущая реализация CLR всегда возвращает `fmFlat` в `pdwMappingType` , но это может измениться в будущих версиях CLR или в будущих выпусках данной версии службы.</span><span class="sxs-lookup"><span data-stu-id="55c47-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="55c47-131">Всегда следует проверять возвращаемое значение в `pdwMappingType` , поскольку разные типы будут иметь разные макеты и смещения.</span><span class="sxs-lookup"><span data-stu-id="55c47-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="55c47-132">Передача значения NULL для любого из трех параметров не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="55c47-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="55c47-133">Метод возвращает значение `E_INVALIDARG` , и ни один из выходных данных не заполнен.</span><span class="sxs-lookup"><span data-stu-id="55c47-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="55c47-134">Пропуск типа сопоставления или размера региона может привести к аварийному завершению программы.</span><span class="sxs-lookup"><span data-stu-id="55c47-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55c47-135">Требования</span><span class="sxs-lookup"><span data-stu-id="55c47-135">Requirements</span></span>  

 <span data-ttu-id="55c47-136">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55c47-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55c47-137">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="55c47-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="55c47-138">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="55c47-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="55c47-139">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55c47-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c47-140">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="55c47-140">See also</span></span>

- [<span data-ttu-id="55c47-141">Интерфейс IMetaDataInfo</span><span class="sxs-lookup"><span data-stu-id="55c47-141">IMetaDataInfo Interface</span></span>](imetadatainfo-interface.md)
- [<span data-ttu-id="55c47-142">Перечисление CorFileMapping</span><span class="sxs-lookup"><span data-stu-id="55c47-142">CorFileMapping Enumeration</span></span>](corfilemapping-enumeration.md)
