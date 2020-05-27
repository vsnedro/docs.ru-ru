---
title: Метод IMetaDataAssemblyEmit::SetManifestResourceProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetManifestResourceProps
helpviewer_keywords:
- SetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetManifestResourceProps method [.NET Framework metadata]
ms.assetid: ef77efd1-849c-4e51-ba92-7ee3d2bf0339
topic_type:
- apiref
ms.openlocfilehash: 74111a175b0decbc1beef7c8df5ade59d31d845b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009149"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="93961-102">Метод IMetaDataAssemblyEmit::SetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="93961-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="93961-103">Изменяет указанную структуру метаданных `ManifestResource`.</span><span class="sxs-lookup"><span data-stu-id="93961-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93961-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93961-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93961-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="93961-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="93961-106">окне Токен, указывающий `ManifestResource` структуру метаданных для изменения.</span><span class="sxs-lookup"><span data-stu-id="93961-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="93961-107">окне Токен типа `File` или `AssemblyRef` , который сопоставляется с поставщиком ресурсов.</span><span class="sxs-lookup"><span data-stu-id="93961-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="93961-108">окне Смещение в начале ресурса в файле.</span><span class="sxs-lookup"><span data-stu-id="93961-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="93961-109">окне Побитовое сочетание значений флагов, задающих атрибуты ресурса.</span><span class="sxs-lookup"><span data-stu-id="93961-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93961-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="93961-110">Remarks</span></span>  
 <span data-ttu-id="93961-111">Чтобы создать `ManifestResource` структуру метаданных, используйте метод [IMetaDataAssemblyEmit::D ефинеманифестресаурце](imetadataassemblyemit-definemanifestresource-method.md) .</span><span class="sxs-lookup"><span data-stu-id="93961-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93961-112">Требования</span><span class="sxs-lookup"><span data-stu-id="93961-112">Requirements</span></span>  
 <span data-ttu-id="93961-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93961-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93961-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="93961-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="93961-115">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="93961-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="93961-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93961-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93961-117">См. также статью</span><span class="sxs-lookup"><span data-stu-id="93961-117">See also</span></span>

- [<span data-ttu-id="93961-118">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="93961-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
