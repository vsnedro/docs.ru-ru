---
title: Метод IMetaDataImport2::GetGenericParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
ms.openlocfilehash: 16f69d571ffed87a2e848124ce16ac942d319c37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702699"
---
# <a name="imetadataimport2getgenericparamprops-method"></a><span data-ttu-id="335c9-102">Метод IMetaDataImport2::GetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="335c9-102">IMetaDataImport2::GetGenericParamProps Method</span></span>

<span data-ttu-id="335c9-103">Возвращает метаданные, связанные с универсальным параметром, представленным указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="335c9-103">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="335c9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="335c9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="335c9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="335c9-105">Parameters</span></span>  

 `gp`  
 <span data-ttu-id="335c9-106">окне Токен, представляющий универсальный параметр, для которого возвращаются метаданные.</span><span class="sxs-lookup"><span data-stu-id="335c9-106">[in] The token that represents the generic parameter for which to return metadata.</span></span>  
  
 `pulParamSeq`  
 <span data-ttu-id="335c9-107">заполняет Порядковый номер `Type` параметра в родительском конструкторе или методе.</span><span class="sxs-lookup"><span data-stu-id="335c9-107">[out] The ordinal position of the `Type` parameter in the parent constructor or method.</span></span>  
  
 `pdwParamFlags`  
 <span data-ttu-id="335c9-108">заполняет Значение перечисления [корженерикпараматтр](corgenericparamattr-enumeration.md) , описывающее объект `Type` для универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="335c9-108">[out] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the `Type` for the generic parameter.</span></span>  
  
 `ptOwner`  
 <span data-ttu-id="335c9-109">заполняет Токен TypeDef или MethodDef, представляющий владельца параметра.</span><span class="sxs-lookup"><span data-stu-id="335c9-109">[out] A TypeDef or MethodDef token that represents the owner of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="335c9-110">заполняет Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="335c9-110">[out] Reserved for future extensibility.</span></span>  
  
 `wzName`  
 <span data-ttu-id="335c9-111">заполняет Имя универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="335c9-111">[out] The name of the generic parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="335c9-112">окне Размер `wzName` буфера.</span><span class="sxs-lookup"><span data-stu-id="335c9-112">[in] The size of the `wzName` buffer.</span></span>  
  
 `pchName`  
 <span data-ttu-id="335c9-113">заполняет Возвращаемый размер имени в расширенных символах.</span><span class="sxs-lookup"><span data-stu-id="335c9-113">[out] The returned size of the name, in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="335c9-114">Требования</span><span class="sxs-lookup"><span data-stu-id="335c9-114">Requirements</span></span>  

 <span data-ttu-id="335c9-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="335c9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="335c9-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="335c9-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="335c9-117">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="335c9-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="335c9-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="335c9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="335c9-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="335c9-119">See also</span></span>

- [<span data-ttu-id="335c9-120">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="335c9-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="335c9-121">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="335c9-121">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
