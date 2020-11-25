---
title: Метод IMetaDataAssemblyImport::EnumExportedTypes
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
ms.openlocfilehash: a8b2377c48331ff9f0e69876c51fb78c7190f694
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708898"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="76639-102">Метод IMetaDataAssemblyImport::EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="76639-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>

<span data-ttu-id="76639-103">Перечисляет экспортированные типы, на которые ссылается манифест сборки в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="76639-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76639-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76639-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76639-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="76639-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="76639-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="76639-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="76639-107">Это значение должно быть null, если `EnumExportedTypes` метод вызывается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="76639-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="76639-108">заполняет Перечисление `mdExportedType` токенов метаданных.</span><span class="sxs-lookup"><span data-stu-id="76639-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="76639-109">окне Максимальное число `mdExportedType` токенов, которые могут быть помещены в `rExportedTypes` массив.</span><span class="sxs-lookup"><span data-stu-id="76639-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="76639-110">заполняет Количество маркеров, которые `mdExportedType` в действительности помещаются в `rExportedTypes` .</span><span class="sxs-lookup"><span data-stu-id="76639-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76639-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="76639-111">Return Value</span></span>  
  
|<span data-ttu-id="76639-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="76639-112">HRESULT</span></span>|<span data-ttu-id="76639-113">Описание</span><span class="sxs-lookup"><span data-stu-id="76639-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="76639-114">`EnumExportedTypes` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="76639-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="76639-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="76639-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="76639-116">В этом случае `pcTokens` имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="76639-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="76639-117">Требования</span><span class="sxs-lookup"><span data-stu-id="76639-117">Requirements</span></span>  

 <span data-ttu-id="76639-118">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76639-118">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76639-119">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="76639-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="76639-120">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="76639-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="76639-121">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76639-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76639-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="76639-122">See also</span></span>

- [<span data-ttu-id="76639-123">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="76639-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
