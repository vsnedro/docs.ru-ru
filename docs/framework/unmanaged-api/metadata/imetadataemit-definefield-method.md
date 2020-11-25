---
title: Метод IMetaDataEmit::DefineField
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
ms.openlocfilehash: 2bc2b983171dc41d5ac37eda0359f1aaee4ebd6e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725759"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="2c080-102">Метод IMetaDataEmit::DefineField</span><span class="sxs-lookup"><span data-stu-id="2c080-102">IMetaDataEmit::DefineField Method</span></span>

<span data-ttu-id="2c080-103">Создает определение для поля с указанной сигнатурой метаданных и получает маркер для этого определения поля.</span><span class="sxs-lookup"><span data-stu-id="2c080-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c080-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c080-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineField (
    [in]  mdTypeDef   td,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwFieldFlags,
    [in]  PCCOR_SIGNATURE pvSigBlob,
    [in]  ULONG       cbSigBlob,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue,
    [out] mdFieldDef  *pmd
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c080-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c080-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="2c080-106">окне `mdTypeDef` Токен для включающего класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2c080-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="2c080-107">окне Имя поля в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="2c080-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="2c080-108">окне Атрибуты поля.</span><span class="sxs-lookup"><span data-stu-id="2c080-108">[in] The field attributes.</span></span> <span data-ttu-id="2c080-109">Это битовая маска `CorFieldAttr` значений.</span><span class="sxs-lookup"><span data-stu-id="2c080-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="2c080-110">окне Подпись поля в виде большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="2c080-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="2c080-111">окне Число байтов в `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="2c080-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="2c080-112">окне `ELEMENT_TYPE_` *\** Значение для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="2c080-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="2c080-113">Это `CorElementType` значение.</span><span class="sxs-lookup"><span data-stu-id="2c080-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="2c080-114">Если для поля не определено постоянное значение, используйте `ELEMENT_TYPE_END` .</span><span class="sxs-lookup"><span data-stu-id="2c080-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="2c080-115">окне Постоянное значение для поля.</span><span class="sxs-lookup"><span data-stu-id="2c080-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="2c080-116">окне Размер символов (в Юникоде) `pValue` .</span><span class="sxs-lookup"><span data-stu-id="2c080-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="2c080-117">заполняет `mdFieldDef` Назначенный маркер.</span><span class="sxs-lookup"><span data-stu-id="2c080-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c080-118">Требования</span><span class="sxs-lookup"><span data-stu-id="2c080-118">Requirements</span></span>  

 <span data-ttu-id="2c080-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c080-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c080-120">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="2c080-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c080-121">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2c080-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c080-122">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c080-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c080-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2c080-123">See also</span></span>

- [<span data-ttu-id="2c080-124">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2c080-124">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2c080-125">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2c080-125">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
