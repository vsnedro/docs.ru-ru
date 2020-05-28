---
title: Метод IMetaDataEmit::DefineProperty
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
ms.openlocfilehash: 479cb25ad8e1c263d3539a4203ac5bea781eb931
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009383"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="459a7-102">Метод IMetaDataEmit::DefineProperty</span><span class="sxs-lookup"><span data-stu-id="459a7-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="459a7-103">Создает определение свойства для указанного типа с указанными `get` `set` методами доступа и и получает маркер для этого определения свойства.</span><span class="sxs-lookup"><span data-stu-id="459a7-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="459a7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="459a7-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineProperty (
    [in]  mdTypeDef          td,
    [in]  LPCWSTR            szProperty,
    [in]  DWORD              dwPropFlags,
    [in]  PCCOR_SIGNATURE    pvSig,
    [in]  ULONG              cbSig,
    [in]  DWORD              dwCPlusTypeFlag,
    [in]  void const         *pValue,
    [in]  ULONG              cchValue,
    [in]  mdMethodDef        mdSetter,
    [in]  mdMethodDef        mdGetter,
    [in]  mdMethodDef        rmdOtherMethods[],
    [out] mdProperty         *pmdProp
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="459a7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="459a7-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="459a7-106">окне Токен для класса или интерфейса, для которого определяется свойство.</span><span class="sxs-lookup"><span data-stu-id="459a7-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="459a7-107">[in] Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="459a7-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="459a7-108">окне Флаги свойств.</span><span class="sxs-lookup"><span data-stu-id="459a7-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="459a7-109">окне Сигнатура свойства.</span><span class="sxs-lookup"><span data-stu-id="459a7-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="459a7-110">окне Число байтов в `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="459a7-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="459a7-111">окне Тип значения свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="459a7-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="459a7-112">окне Значение по умолчанию для свойства.</span><span class="sxs-lookup"><span data-stu-id="459a7-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="459a7-113">окне Число символов Юникода в `pValue` .</span><span class="sxs-lookup"><span data-stu-id="459a7-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="459a7-114">окне Метод, который задает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="459a7-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="459a7-115">окне Метод, который получает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="459a7-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="459a7-116">окне Массив других методов, связанных со свойством.</span><span class="sxs-lookup"><span data-stu-id="459a7-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="459a7-117">Завершите массив с помощью `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="459a7-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="459a7-118">заполняет `mdProperty`Назначенный маркер.</span><span class="sxs-lookup"><span data-stu-id="459a7-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="459a7-119">Требования</span><span class="sxs-lookup"><span data-stu-id="459a7-119">Requirements</span></span>  
 <span data-ttu-id="459a7-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="459a7-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="459a7-121">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="459a7-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="459a7-122">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="459a7-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="459a7-123">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="459a7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="459a7-124">См. также статью</span><span class="sxs-lookup"><span data-stu-id="459a7-124">See also</span></span>

- [<span data-ttu-id="459a7-125">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="459a7-125">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="459a7-126">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="459a7-126">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
