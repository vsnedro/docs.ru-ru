---
title: Метод IMetaDataImport::EnumFieldsWithName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFieldsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFieldsWithName
helpviewer_keywords:
- IMetaDataImport::EnumFieldsWithName method [.NET Framework metadata]
- EnumFieldsWithName method [.NET Framework metadata]
ms.assetid: 42145e8d-000f-4d0b-ae43-c08201190fa2
topic_type:
- apiref
ms.openlocfilehash: 0a254587282dea43a3507fbbeca35bd7aa9604f3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711576"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="944db-102">Метод IMetaDataImport::EnumFieldsWithName</span><span class="sxs-lookup"><span data-stu-id="944db-102">IMetaDataImport::EnumFieldsWithName Method</span></span>

<span data-ttu-id="944db-103">Перечисляет токены FieldDef заданного типа с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="944db-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="944db-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="944db-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,
   [in]  mdTypeDef       cl,
   [in]  LPCWSTR         szName,
   [out] mdFieldDef      rFields[],
   [in]  ULONG           cMax,
   [out] ULONG           *pcTokens
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="944db-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="944db-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="944db-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="944db-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="944db-107">окне Токен типа, поля которого необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="944db-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="944db-108">окне Имя поля, ограничивающее область перечисления.</span><span class="sxs-lookup"><span data-stu-id="944db-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="944db-109">заполняет Массив, используемый для хранения маркеров FieldDef.</span><span class="sxs-lookup"><span data-stu-id="944db-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="944db-110">[in] Максимальный размер массива `rFields`.</span><span class="sxs-lookup"><span data-stu-id="944db-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="944db-111">заполняет Фактическое число токенов FieldDef, возвращаемых в `rFields` .</span><span class="sxs-lookup"><span data-stu-id="944db-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="944db-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="944db-112">Remarks</span></span>  

 <span data-ttu-id="944db-113">В отличие от [IMetaDataImport:: EnumFields](imetadataimport-enumfields-method.md), `EnumFieldsWithName` отменяет все маркеры полей, у которых нет указанного имени.</span><span class="sxs-lookup"><span data-stu-id="944db-113">Unlike [IMetaDataImport::EnumFields](imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="944db-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="944db-114">Return Value</span></span>  
  
|<span data-ttu-id="944db-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="944db-115">HRESULT</span></span>|<span data-ttu-id="944db-116">Описание</span><span class="sxs-lookup"><span data-stu-id="944db-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="944db-117">`EnumFieldsWithName` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="944db-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="944db-118">Нет полей для перечисления.</span><span class="sxs-lookup"><span data-stu-id="944db-118">There are no fields to enumerate.</span></span> <span data-ttu-id="944db-119">В этом случае значение `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="944db-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="944db-120">Требования</span><span class="sxs-lookup"><span data-stu-id="944db-120">Requirements</span></span>  

 <span data-ttu-id="944db-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="944db-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="944db-122">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="944db-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="944db-123">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="944db-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="944db-124">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="944db-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="944db-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="944db-125">See also</span></span>

- [<span data-ttu-id="944db-126">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="944db-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="944db-127">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="944db-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
