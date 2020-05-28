---
title: Метод IMetaDataDispenser::DefineScope
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.DefineScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type:
- apiref
ms.openlocfilehash: 021ef8de602d6dd928f49e69e36f8d4a61425745
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008369"
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="66929-102">Метод IMetaDataDispenser::DefineScope</span><span class="sxs-lookup"><span data-stu-id="66929-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="66929-103">Создает новую область в памяти, в которой можно создавать новые метаданные.</span><span class="sxs-lookup"><span data-stu-id="66929-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66929-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66929-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66929-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="66929-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="66929-106">окне Идентификатор CLSID версии создаваемых структур метаданных.</span><span class="sxs-lookup"><span data-stu-id="66929-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="66929-107">Это значение должно быть CLSID_CorMetaDataRuntime для .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="66929-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="66929-108">окне Флаги, указывающие параметры.</span><span class="sxs-lookup"><span data-stu-id="66929-108">[in] Flags that specify options.</span></span> <span data-ttu-id="66929-109">Для .NET Framework 2,0 это значение должно быть равно нулю.</span><span class="sxs-lookup"><span data-stu-id="66929-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="66929-110">окне Идентификатор IID требуемого интерфейса метаданных, который должен быть возвращен; вызывающий объект будет использовать интерфейс для создания новых метаданных.</span><span class="sxs-lookup"><span data-stu-id="66929-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="66929-111">Значение `riid` должно указывать один из интерфейсов "Emit".</span><span class="sxs-lookup"><span data-stu-id="66929-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="66929-112">Допустимые значения: IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit или IID_IMetaDataEmit2.</span><span class="sxs-lookup"><span data-stu-id="66929-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="66929-113">заполняет Указатель на возвращаемый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="66929-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66929-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="66929-114">Remarks</span></span>  
 <span data-ttu-id="66929-115">`DefineScope`создает набор таблиц метаданных в памяти, создает уникальный идентификатор GUID (идентификатор версии модуля или MVID) для метаданных и создает запись в таблице Module для выдаваемой единицы компиляции.</span><span class="sxs-lookup"><span data-stu-id="66929-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="66929-116">Вы можете прикрепить атрибуты к области метаданных в целом с помощью метода [IMetaDataEmit:: сетмодулепропс](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) или [IMetaDataEmit::D ефинекустоматтрибуте](imetadataemit-definecustomattribute-method.md) , в зависимости от ситуации.</span><span class="sxs-lookup"><span data-stu-id="66929-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66929-117">Требования</span><span class="sxs-lookup"><span data-stu-id="66929-117">Requirements</span></span>  
 <span data-ttu-id="66929-118">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66929-118">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66929-119">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="66929-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="66929-120">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="66929-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="66929-121">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66929-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66929-122">См. также статью</span><span class="sxs-lookup"><span data-stu-id="66929-122">See also</span></span>

- [<span data-ttu-id="66929-123">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="66929-123">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="66929-124">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="66929-124">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="66929-125">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="66929-125">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="66929-126">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="66929-126">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="66929-127">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="66929-127">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
