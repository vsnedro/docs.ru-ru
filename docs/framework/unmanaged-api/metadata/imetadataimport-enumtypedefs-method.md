---
title: Метод IMetaDataImport::EnumTypeDefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
ms.openlocfilehash: cdfd4e10236d546af2555b125d44233172849a21
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503735"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="bb4aa-102">Метод IMetaDataImport::EnumTypeDefs</span><span class="sxs-lookup"><span data-stu-id="bb4aa-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="bb4aa-103">Перечисляет токены TypeDef, представляющие все типы в текущей области.</span><span class="sxs-lookup"><span data-stu-id="bb4aa-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb4aa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb4aa-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb4aa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb4aa-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="bb4aa-106">заполняет Указатель на новый перечислитель.</span><span class="sxs-lookup"><span data-stu-id="bb4aa-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="bb4aa-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="bb4aa-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="bb4aa-108">окне Массив, используемый для хранения токенов TypeDef.</span><span class="sxs-lookup"><span data-stu-id="bb4aa-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bb4aa-109">[in] Максимальный размер массива `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="bb4aa-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="bb4aa-110">заполняет Число токенов TypeDef, возвращаемых в `rTypeDefs` .</span><span class="sxs-lookup"><span data-stu-id="bb4aa-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb4aa-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bb4aa-111">Return Value</span></span>  
  
|<span data-ttu-id="bb4aa-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bb4aa-112">HRESULT</span></span>|<span data-ttu-id="bb4aa-113">Описание</span><span class="sxs-lookup"><span data-stu-id="bb4aa-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="bb4aa-114">`EnumTypeDefs`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="bb4aa-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="bb4aa-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="bb4aa-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="bb4aa-116">В этом случае значение `pcTypeDefs` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="bb4aa-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb4aa-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="bb4aa-117">Remarks</span></span>  
 <span data-ttu-id="bb4aa-118">Маркер TypeDef представляет тип, например класс или интерфейс, а также любой тип, добавленный с помощью механизма расширяемости.</span><span class="sxs-lookup"><span data-stu-id="bb4aa-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb4aa-119">Требования</span><span class="sxs-lookup"><span data-stu-id="bb4aa-119">Requirements</span></span>  
 <span data-ttu-id="bb4aa-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb4aa-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb4aa-121">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="bb4aa-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bb4aa-122">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bb4aa-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bb4aa-123">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb4aa-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb4aa-124">См. также</span><span class="sxs-lookup"><span data-stu-id="bb4aa-124">See also</span></span>

- [<span data-ttu-id="bb4aa-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="bb4aa-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="bb4aa-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="bb4aa-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
