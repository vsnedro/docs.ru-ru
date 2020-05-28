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
ms.openlocfilehash: ccc4843864f375c167acdb12575c282dbe3a49e1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004820"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="9f45a-102">Метод IMetaDataEmit::DefineField</span><span class="sxs-lookup"><span data-stu-id="9f45a-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="9f45a-103">Создает определение для поля с указанной сигнатурой метаданных и получает маркер для этого определения поля.</span><span class="sxs-lookup"><span data-stu-id="9f45a-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f45a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f45a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="9f45a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9f45a-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="9f45a-106">окне `mdTypeDef`Токен для включающего класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9f45a-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="9f45a-107">окне Имя поля в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="9f45a-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="9f45a-108">окне Атрибуты поля.</span><span class="sxs-lookup"><span data-stu-id="9f45a-108">[in] The field attributes.</span></span> <span data-ttu-id="9f45a-109">Это битовая маска `CorFieldAttr` значений.</span><span class="sxs-lookup"><span data-stu-id="9f45a-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="9f45a-110">окне Подпись поля в виде большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="9f45a-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="9f45a-111">окне Число байтов в `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="9f45a-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="9f45a-112">окне `ELEMENT_TYPE_` *\** Значение для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="9f45a-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="9f45a-113">Это `CorElementType` значение.</span><span class="sxs-lookup"><span data-stu-id="9f45a-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="9f45a-114">Если для поля не определено постоянное значение, используйте `ELEMENT_TYPE_END` .</span><span class="sxs-lookup"><span data-stu-id="9f45a-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="9f45a-115">окне Постоянное значение для поля.</span><span class="sxs-lookup"><span data-stu-id="9f45a-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="9f45a-116">окне Размер символов (в Юникоде) `pValue` .</span><span class="sxs-lookup"><span data-stu-id="9f45a-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="9f45a-117">заполняет `mdFieldDef`Назначенный маркер.</span><span class="sxs-lookup"><span data-stu-id="9f45a-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f45a-118">Требования</span><span class="sxs-lookup"><span data-stu-id="9f45a-118">Requirements</span></span>  
 <span data-ttu-id="9f45a-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f45a-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f45a-120">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="9f45a-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9f45a-121">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9f45a-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f45a-122">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f45a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f45a-123">См. также статью</span><span class="sxs-lookup"><span data-stu-id="9f45a-123">See also</span></span>

- [<span data-ttu-id="9f45a-124">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="9f45a-124">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="9f45a-125">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="9f45a-125">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
