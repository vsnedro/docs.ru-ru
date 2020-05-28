---
title: Метод IMetaDataEmit::SetParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
ms.openlocfilehash: b710f966f519e2702607b7e186fff5986110d391
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007823"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="8d6bd-102">Метод IMetaDataEmit::SetParamProps</span><span class="sxs-lookup"><span data-stu-id="8d6bd-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="8d6bd-103">Задает или изменяет функции параметра метода, который был определен при предыдущем вызове [IMetaDataEmit::D ефинепарам](imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="8d6bd-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d6bd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d6bd-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParamProps (
    [in]  mdParamDef  pd,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d6bd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8d6bd-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="8d6bd-106">окне Токен для целевого параметра.</span><span class="sxs-lookup"><span data-stu-id="8d6bd-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="8d6bd-107">окне Имя параметра в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="8d6bd-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="8d6bd-108">окне Флаги для параметра.</span><span class="sxs-lookup"><span data-stu-id="8d6bd-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="8d6bd-109">окне ELEMENT_TYPE_ \* для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="8d6bd-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="8d6bd-110">окне Постоянное значение для параметра.</span><span class="sxs-lookup"><span data-stu-id="8d6bd-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="8d6bd-111">окне Размер символов (в Юникоде) `pValue` .</span><span class="sxs-lookup"><span data-stu-id="8d6bd-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d6bd-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8d6bd-112">Requirements</span></span>  
 <span data-ttu-id="8d6bd-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d6bd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d6bd-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="8d6bd-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8d6bd-115">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8d6bd-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d6bd-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d6bd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d6bd-117">См. также статью</span><span class="sxs-lookup"><span data-stu-id="8d6bd-117">See also</span></span>

- [<span data-ttu-id="8d6bd-118">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="8d6bd-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8d6bd-119">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="8d6bd-119">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
