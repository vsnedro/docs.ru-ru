---
title: Метод IMetaDataImport::EnumFields
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFields
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFields
helpviewer_keywords:
- EnumFields method [.NET Framework metadata]
- IMetaDataImport::EnumFields method [.NET Framework metadata]
ms.assetid: 1d23247e-c58c-45db-afd8-83aa89cde18e
topic_type:
- apiref
ms.openlocfilehash: 74035e9551cb1d622b326e511c3884e1eadf057f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711602"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="01dcb-102">Метод IMetaDataImport::EnumFields</span><span class="sxs-lookup"><span data-stu-id="01dcb-102">IMetaDataImport::EnumFields Method</span></span>

<span data-ttu-id="01dcb-103">Перечисляет токены FieldDef для типа, на который ссылается указанный токен TypeDef.</span><span class="sxs-lookup"><span data-stu-id="01dcb-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01dcb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01dcb-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFields (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [out]     mdFieldDef  rFields[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01dcb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="01dcb-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="01dcb-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="01dcb-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="01dcb-107">окне Токен TypeDef класса, поля которого необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="01dcb-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="01dcb-108">заполняет Список токенов FieldDef.</span><span class="sxs-lookup"><span data-stu-id="01dcb-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="01dcb-109">[in] Максимальный размер массива `rFields`.</span><span class="sxs-lookup"><span data-stu-id="01dcb-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="01dcb-110">заполняет Фактическое число токенов FieldDef, возвращаемых в `rFields` .</span><span class="sxs-lookup"><span data-stu-id="01dcb-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01dcb-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="01dcb-111">Return Value</span></span>  
  
|<span data-ttu-id="01dcb-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="01dcb-112">HRESULT</span></span>|<span data-ttu-id="01dcb-113">Описание</span><span class="sxs-lookup"><span data-stu-id="01dcb-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="01dcb-114">`EnumFields` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="01dcb-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="01dcb-115">Нет полей для перечисления.</span><span class="sxs-lookup"><span data-stu-id="01dcb-115">There are no fields to enumerate.</span></span> <span data-ttu-id="01dcb-116">В этом случае значение `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="01dcb-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="01dcb-117">Требования</span><span class="sxs-lookup"><span data-stu-id="01dcb-117">Requirements</span></span>  

 <span data-ttu-id="01dcb-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01dcb-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01dcb-119">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="01dcb-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="01dcb-120">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="01dcb-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="01dcb-121">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01dcb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01dcb-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="01dcb-122">See also</span></span>

- [<span data-ttu-id="01dcb-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="01dcb-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="01dcb-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="01dcb-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
