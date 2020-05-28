---
title: Метод IMetaDataEmit::DefineParam
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type:
- apiref
ms.openlocfilehash: a58e03875ec021b41479085fa9e27a4321ae965e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004378"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="06242-102">Метод IMetaDataEmit::DefineParam</span><span class="sxs-lookup"><span data-stu-id="06242-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="06242-103">Создает определение параметра с указанной сигнатурой для метода, на который ссылается указанный токен, и получает маркер для этого определения параметра.</span><span class="sxs-lookup"><span data-stu-id="06242-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06242-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06242-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineParam (  
    [in]  mdMethodDef md,
    [in]  ULONG       ulParamSeq,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,
    [out] mdParamDef  *ppd
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06242-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="06242-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="06242-106">окне Токен для метода, параметр которого определяется.</span><span class="sxs-lookup"><span data-stu-id="06242-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="06242-107">окне Порядковый номер параметра.</span><span class="sxs-lookup"><span data-stu-id="06242-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="06242-108">окне Имя параметра в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="06242-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="06242-109">окне Флаги для параметра.</span><span class="sxs-lookup"><span data-stu-id="06242-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="06242-110">Это битовая маска `CorParamAttr` значений.</span><span class="sxs-lookup"><span data-stu-id="06242-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="06242-111">[входные] `ELEMENT_TYPE_` *\** для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="06242-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="06242-112">окне Постоянное значение для параметра.</span><span class="sxs-lookup"><span data-stu-id="06242-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="06242-113">окне Размер (в символах Юникода) `pValue` .</span><span class="sxs-lookup"><span data-stu-id="06242-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="06242-114">заполняет `mdParamDef`Назначенный маркер.</span><span class="sxs-lookup"><span data-stu-id="06242-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06242-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="06242-115">Remarks</span></span>  
 <span data-ttu-id="06242-116">Значения последовательности в `ulParamSeq` аргументе начинаются с 1 для параметров.</span><span class="sxs-lookup"><span data-stu-id="06242-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="06242-117">Возвращаемое значение имеет порядковый номер 0.</span><span class="sxs-lookup"><span data-stu-id="06242-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06242-118">Требования</span><span class="sxs-lookup"><span data-stu-id="06242-118">Requirements</span></span>  
 <span data-ttu-id="06242-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06242-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06242-120">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="06242-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06242-121">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="06242-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06242-122">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06242-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06242-123">См. также статью</span><span class="sxs-lookup"><span data-stu-id="06242-123">See also</span></span>

- [<span data-ttu-id="06242-124">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="06242-124">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="06242-125">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="06242-125">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
