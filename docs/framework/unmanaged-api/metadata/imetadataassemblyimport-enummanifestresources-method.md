---
title: Метод IMetaDataAssemblyImport::EnumManifestResources
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumManifestResources
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type:
- apiref
ms.openlocfilehash: c72e5b9544d1d8ae989405ac9bfdb22050b1aaaf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731623"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="b15c8-102">Метод IMetaDataAssemblyImport::EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="b15c8-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>

<span data-ttu-id="b15c8-103">Возвращает указатель на перечислитель для ресурсов, указанных в текущем манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="b15c8-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b15c8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b15c8-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,
    [out] mdManifestResource   rManifestResources[],
    [in]  ULONG                cMax,
    [out] ULONG                *pcTokens  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="b15c8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b15c8-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="b15c8-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="b15c8-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b15c8-107">Это значение должно быть null, если `EnumManifestResources` метод вызывается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="b15c8-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="b15c8-108">заполняет Массив, используемый для хранения `mdManifestResource` маркеров метаданных.</span><span class="sxs-lookup"><span data-stu-id="b15c8-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b15c8-109">окне Максимальное число `mdManifestResource` токенов, которые могут быть помещены в `rManifestResources` .</span><span class="sxs-lookup"><span data-stu-id="b15c8-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b15c8-110">заполняет Количество маркеров, которые `mdManifestResource` в действительности помещаются в `rManifestResources` .</span><span class="sxs-lookup"><span data-stu-id="b15c8-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b15c8-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b15c8-111">Return Value</span></span>  
  
|<span data-ttu-id="b15c8-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b15c8-112">HRESULT</span></span>|<span data-ttu-id="b15c8-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b15c8-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b15c8-114">`EnumManifestResources` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="b15c8-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b15c8-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="b15c8-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="b15c8-116">В этом случае `pcTokens` имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="b15c8-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b15c8-117">Требования</span><span class="sxs-lookup"><span data-stu-id="b15c8-117">Requirements</span></span>  

 <span data-ttu-id="b15c8-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b15c8-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b15c8-119">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="b15c8-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b15c8-120">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b15c8-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b15c8-121">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b15c8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b15c8-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b15c8-122">See also</span></span>

- [<span data-ttu-id="b15c8-123">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="b15c8-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
