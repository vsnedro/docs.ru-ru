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
ms.openlocfilehash: 4545f5f8d78e588c655a72340210a785b0feb619
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720416"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="a40d0-102">Метод IMetaDataImport::EnumTypeDefs</span><span class="sxs-lookup"><span data-stu-id="a40d0-102">IMetaDataImport::EnumTypeDefs Method</span></span>

<span data-ttu-id="a40d0-103">Перечисляет токены TypeDef, представляющие все типы в текущей области.</span><span class="sxs-lookup"><span data-stu-id="a40d0-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a40d0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a40d0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a40d0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a40d0-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="a40d0-106">заполняет Указатель на новый перечислитель.</span><span class="sxs-lookup"><span data-stu-id="a40d0-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="a40d0-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="a40d0-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="a40d0-108">окне Массив, используемый для хранения токенов TypeDef.</span><span class="sxs-lookup"><span data-stu-id="a40d0-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a40d0-109">[in] Максимальный размер массива `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="a40d0-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="a40d0-110">заполняет Число токенов TypeDef, возвращаемых в `rTypeDefs` .</span><span class="sxs-lookup"><span data-stu-id="a40d0-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a40d0-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a40d0-111">Return Value</span></span>  
  
|<span data-ttu-id="a40d0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a40d0-112">HRESULT</span></span>|<span data-ttu-id="a40d0-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a40d0-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a40d0-114">`EnumTypeDefs` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="a40d0-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a40d0-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="a40d0-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="a40d0-116">В этом случае значение `pcTypeDefs` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="a40d0-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a40d0-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a40d0-117">Remarks</span></span>  

 <span data-ttu-id="a40d0-118">Маркер TypeDef представляет тип, например класс или интерфейс, а также любой тип, добавленный с помощью механизма расширяемости.</span><span class="sxs-lookup"><span data-stu-id="a40d0-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a40d0-119">Требования</span><span class="sxs-lookup"><span data-stu-id="a40d0-119">Requirements</span></span>  

 <span data-ttu-id="a40d0-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a40d0-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a40d0-121">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="a40d0-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a40d0-122">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a40d0-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a40d0-123">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a40d0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a40d0-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a40d0-124">See also</span></span>

- [<span data-ttu-id="a40d0-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a40d0-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a40d0-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a40d0-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
