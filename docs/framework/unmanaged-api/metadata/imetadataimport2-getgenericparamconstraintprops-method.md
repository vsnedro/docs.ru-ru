---
title: Метод IMetaDataImport2::GetGenericParamConstraintProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamConstraintProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps method [.NET Framework metadata]
- GetGenericParamConstraintProps method [.NET Framework metadata]
ms.assetid: c5fee4a0-b132-4e5e-8730-e586ce314b9a
topic_type:
- apiref
ms.openlocfilehash: 8beaea0b7493b7cea76466bb15355cfc5c6d5c7d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702710"
---
# <a name="imetadataimport2getgenericparamconstraintprops-method"></a><span data-ttu-id="7aa53-102">Метод IMetaDataImport2::GetGenericParamConstraintProps</span><span class="sxs-lookup"><span data-stu-id="7aa53-102">IMetaDataImport2::GetGenericParamConstraintProps Method</span></span>

<span data-ttu-id="7aa53-103">Возвращает метаданные, связанные с ограничением универсального параметра, представленного указанным маркером ограничения.</span><span class="sxs-lookup"><span data-stu-id="7aa53-103">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aa53-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7aa53-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenericParamConstraintProps (  
   [in]  mdGenericParamConstraint  gpc,  
   [out] mdGenericParam            *ptGenericParam,  
   [out] mdToken                   *ptkConstraintType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7aa53-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7aa53-105">Parameters</span></span>  

 `gpc`  
 <span data-ttu-id="7aa53-106">окне Токен для ограничения универсального параметра, для которого возвращаются метаданные.</span><span class="sxs-lookup"><span data-stu-id="7aa53-106">[in] The token to the generic parameter constraint for which to return the metadata.</span></span>  
  
 `ptGenericParam`  
 <span data-ttu-id="7aa53-107">заполняет Указатель на маркер, представляющий ограниченный универсальный параметр.</span><span class="sxs-lookup"><span data-stu-id="7aa53-107">[out] A pointer to the token that represents the generic parameter that is constrained.</span></span>  
  
 `ptkConstraintType`  
 <span data-ttu-id="7aa53-108">заполняет Указатель на маркер TypeDef, TypeRef или TypeSpec, представляющий ограничение на `ptGenericParam` .</span><span class="sxs-lookup"><span data-stu-id="7aa53-108">[out] A pointer to a TypeDef, TypeRef, or TypeSpec token that represents a constraint on `ptGenericParam`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7aa53-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7aa53-109">Requirements</span></span>  

 <span data-ttu-id="7aa53-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7aa53-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7aa53-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="7aa53-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7aa53-112">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7aa53-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7aa53-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7aa53-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aa53-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7aa53-114">See also</span></span>

- [<span data-ttu-id="7aa53-115">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="7aa53-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="7aa53-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="7aa53-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
