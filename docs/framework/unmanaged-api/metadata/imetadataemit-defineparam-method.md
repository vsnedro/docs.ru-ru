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
ms.openlocfilehash: 5b3f89bb14be0d7128682f8702548545b1e50928
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719532"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="2d50a-102">Метод IMetaDataEmit::DefineParam</span><span class="sxs-lookup"><span data-stu-id="2d50a-102">IMetaDataEmit::DefineParam Method</span></span>

<span data-ttu-id="2d50a-103">Создает определение параметра с указанной сигнатурой для метода, на который ссылается указанный токен, и получает маркер для этого определения параметра.</span><span class="sxs-lookup"><span data-stu-id="2d50a-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d50a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d50a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2d50a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2d50a-105">Parameters</span></span>  

 `md`  
 <span data-ttu-id="2d50a-106">окне Токен для метода, параметр которого определяется.</span><span class="sxs-lookup"><span data-stu-id="2d50a-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="2d50a-107">окне Порядковый номер параметра.</span><span class="sxs-lookup"><span data-stu-id="2d50a-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="2d50a-108">окне Имя параметра в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="2d50a-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="2d50a-109">окне Флаги для параметра.</span><span class="sxs-lookup"><span data-stu-id="2d50a-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="2d50a-110">Это битовая маска `CorParamAttr` значений.</span><span class="sxs-lookup"><span data-stu-id="2d50a-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="2d50a-111">[входные] `ELEMENT_TYPE_` *\** для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="2d50a-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="2d50a-112">окне Постоянное значение для параметра.</span><span class="sxs-lookup"><span data-stu-id="2d50a-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="2d50a-113">окне Размер (в символах Юникода) `pValue` .</span><span class="sxs-lookup"><span data-stu-id="2d50a-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="2d50a-114">заполняет `mdParamDef` Назначенный маркер.</span><span class="sxs-lookup"><span data-stu-id="2d50a-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d50a-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2d50a-115">Remarks</span></span>  

 <span data-ttu-id="2d50a-116">Значения последовательности в `ulParamSeq` аргументе начинаются с 1 для параметров.</span><span class="sxs-lookup"><span data-stu-id="2d50a-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="2d50a-117">Возвращаемое значение имеет порядковый номер 0.</span><span class="sxs-lookup"><span data-stu-id="2d50a-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d50a-118">Требования</span><span class="sxs-lookup"><span data-stu-id="2d50a-118">Requirements</span></span>  

 <span data-ttu-id="2d50a-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d50a-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d50a-120">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="2d50a-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2d50a-121">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2d50a-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d50a-122">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d50a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d50a-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2d50a-123">See also</span></span>

- [<span data-ttu-id="2d50a-124">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2d50a-124">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2d50a-125">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2d50a-125">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
