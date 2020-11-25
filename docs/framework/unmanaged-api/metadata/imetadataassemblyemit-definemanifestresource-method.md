---
title: Метод IMetaDataAssemblyEmit::DefineManifestResource
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineManifestResource
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type:
- apiref
ms.openlocfilehash: 3729f06097fa4dce6de009307183d5e97c24479b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728307"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="99fc5-102">Метод IMetaDataAssemblyEmit::DefineManifestResource</span><span class="sxs-lookup"><span data-stu-id="99fc5-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>

<span data-ttu-id="99fc5-103">Создает структуру `ManifestResource`, содержащую метаданные для указанного ресурса манифеста, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="99fc5-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99fc5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99fc5-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,
    [in] mdToken                tkImplementation,
    [in] DWORD                  dwOffset,
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99fc5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="99fc5-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="99fc5-106">[in] Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="99fc5-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="99fc5-107">окне Маркер метаданных типа `mdtFile` или `mdtAssemblyRef` , сопоставляемый с поставщиком ресурсов.</span><span class="sxs-lookup"><span data-stu-id="99fc5-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="99fc5-108">Значение NULL указывает, что файл, в котором внедрены метаданные, является поставщиком ресурсов.</span><span class="sxs-lookup"><span data-stu-id="99fc5-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="99fc5-109">окне Смещение в начале ресурса в файле.</span><span class="sxs-lookup"><span data-stu-id="99fc5-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="99fc5-110">Для ресурсов в отдельных файлах это значение всегда будет равно нулю.</span><span class="sxs-lookup"><span data-stu-id="99fc5-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="99fc5-111">Если ресурс внедряется в PE-файл, это смещение большого двоичного объекта ресурса, которое начинается в расположении, указанном в файле заголовка COR. h.</span><span class="sxs-lookup"><span data-stu-id="99fc5-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="99fc5-112">окне Побитовое сочетание значений флагов, задающих настройки свойств для определения ресурса.</span><span class="sxs-lookup"><span data-stu-id="99fc5-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="99fc5-113">заполняет Указатель на возвращаемый маркер метаданных.</span><span class="sxs-lookup"><span data-stu-id="99fc5-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99fc5-114">Комментарии</span><span class="sxs-lookup"><span data-stu-id="99fc5-114">Remarks</span></span>  

 <span data-ttu-id="99fc5-115">`ManifestResource`Для каждого ресурса, реализованного в каждом файле сборки, должна быть определена одна структура метаданных.</span><span class="sxs-lookup"><span data-stu-id="99fc5-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99fc5-116">Требования</span><span class="sxs-lookup"><span data-stu-id="99fc5-116">Requirements</span></span>  

 <span data-ttu-id="99fc5-117">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99fc5-117">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99fc5-118">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="99fc5-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="99fc5-119">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="99fc5-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="99fc5-120">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99fc5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99fc5-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="99fc5-121">See also</span></span>

- [<span data-ttu-id="99fc5-122">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="99fc5-122">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
