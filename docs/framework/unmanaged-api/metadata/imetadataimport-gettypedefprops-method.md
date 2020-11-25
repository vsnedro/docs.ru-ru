---
title: Метод IMetaDataImport::GetTypeDefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
ms.openlocfilehash: 9dd973fe3e0802c49c220db51a21c223730e5aec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729174"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="cc66f-102">Метод IMetaDataImport::GetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="cc66f-102">IMetaDataImport::GetTypeDefProps Method</span></span>

<span data-ttu-id="cc66f-103">Возвращает сведения о метаданных для, <xref:System.Type> представленного указанным маркером TypeDef.</span><span class="sxs-lookup"><span data-stu-id="cc66f-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc66f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc66f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc66f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cc66f-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="cc66f-106">окне Токен TypeDef, представляющий тип, для которого возвращаются метаданные.</span><span class="sxs-lookup"><span data-stu-id="cc66f-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="cc66f-107">заполняет Буфер, содержащий имя типа.</span><span class="sxs-lookup"><span data-stu-id="cc66f-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="cc66f-108">окне Размер в расширенных символах `szTypeDef` .</span><span class="sxs-lookup"><span data-stu-id="cc66f-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="cc66f-109">заполняет Число расширенных символов, возвращаемых в `szTypeDef` .</span><span class="sxs-lookup"><span data-stu-id="cc66f-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="cc66f-110">заполняет Указатель на любые флаги, изменяющие определение типа.</span><span class="sxs-lookup"><span data-stu-id="cc66f-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="cc66f-111">Это значение является битовой маской из перечисления [кортипеаттр](cortypeattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="cc66f-111">This value is a bitmask from the [CorTypeAttr](cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="cc66f-112">заполняет Токен метаданных TypeDef или TypeRef, представляющий базовый тип запрошенного типа.</span><span class="sxs-lookup"><span data-stu-id="cc66f-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc66f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="cc66f-113">Requirements</span></span>  

 <span data-ttu-id="cc66f-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc66f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc66f-115">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="cc66f-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cc66f-116">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cc66f-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cc66f-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc66f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc66f-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cc66f-118">See also</span></span>

- [<span data-ttu-id="cc66f-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="cc66f-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="cc66f-120">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="cc66f-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
