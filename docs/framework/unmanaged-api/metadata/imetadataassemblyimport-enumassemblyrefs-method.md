---
title: Метод IMetaDataAssemblyImport::EnumAssemblyRefs
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
ms.openlocfilehash: 1b9700455da82fc7f4a39d4c208ac0b18ef79722
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009123"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="cfb0b-102">Метод IMetaDataAssemblyImport::EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="cfb0b-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="cfb0b-103">Перечисляет `mdAssemblyRef` экземпляры, определенные в манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfb0b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cfb0b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfb0b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cfb0b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="cfb0b-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="cfb0b-107">Это значение должно быть null, если `EnumAssemblyRefs` метод вызывается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="cfb0b-108">заполняет Перечисление `mdAssemblyRef` токенов метаданных.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="cfb0b-109">окне Максимальное число токенов, которые могут быть помещены в `rAssemblyRefs` массив.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="cfb0b-110">заполняет Количество маркеров, которые в действительности помещаются в `rAssemblyRefs` .</span><span class="sxs-lookup"><span data-stu-id="cfb0b-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cfb0b-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cfb0b-111">Return Value</span></span>  
  
|<span data-ttu-id="cfb0b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cfb0b-112">HRESULT</span></span>|<span data-ttu-id="cfb0b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="cfb0b-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="cfb0b-114">`EnumAssemblyRefs`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="cfb0b-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="cfb0b-116">В этом случае `pcTokens` имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cfb0b-117">Требования</span><span class="sxs-lookup"><span data-stu-id="cfb0b-117">Requirements</span></span>  
 <span data-ttu-id="cfb0b-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfb0b-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfb0b-119">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="cfb0b-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cfb0b-120">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cfb0b-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cfb0b-121">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfb0b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfb0b-122">См. также статью</span><span class="sxs-lookup"><span data-stu-id="cfb0b-122">See also</span></span>

- [<span data-ttu-id="cfb0b-123">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="cfb0b-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
