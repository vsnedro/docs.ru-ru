---
title: Метод IMetaDataImport::EnumModuleRefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumModuleRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumModuleRefs
helpviewer_keywords:
- EnumModuleRefs method [.NET Framework metadata]
- IMetaDataImport::EnumModuleRefs method [.NET Framework metadata]
ms.assetid: 53441f3a-68d2-477c-906e-37c55dfcfb4d
topic_type:
- apiref
ms.openlocfilehash: fe7350e6d8e400ae37b5b8b7854a56f3c5c53ea7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491763"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="f2219-102">Метод IMetaDataImport::EnumModuleRefs</span><span class="sxs-lookup"><span data-stu-id="f2219-102">IMetaDataImport::EnumModuleRefs Method</span></span>
<span data-ttu-id="f2219-103">Перечисляет токены ModuleRef, представляющие импортируемые модули.</span><span class="sxs-lookup"><span data-stu-id="f2219-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2219-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2219-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2219-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f2219-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f2219-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="f2219-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="f2219-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="f2219-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="f2219-108">заполняет Массив, используемый для хранения маркеров ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="f2219-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f2219-109">[in] Максимальный размер массива `rModuleRefs`.</span><span class="sxs-lookup"><span data-stu-id="f2219-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="f2219-110">заполняет Число токенов ModuleRef, возвращаемых в `rModuleRefs` .</span><span class="sxs-lookup"><span data-stu-id="f2219-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2219-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f2219-111">Return Value</span></span>  
  
|<span data-ttu-id="f2219-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2219-112">HRESULT</span></span>|<span data-ttu-id="f2219-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f2219-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f2219-114">`EnumModuleRefs`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="f2219-114">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f2219-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="f2219-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="f2219-116">В этом случае значение `pcModuleRefs` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="f2219-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2219-117">Требования</span><span class="sxs-lookup"><span data-stu-id="f2219-117">Requirements</span></span>  
 <span data-ttu-id="f2219-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2219-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2219-119">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="f2219-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2219-120">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f2219-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f2219-121">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2219-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2219-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f2219-122">See also</span></span>

- [<span data-ttu-id="f2219-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f2219-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f2219-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="f2219-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
