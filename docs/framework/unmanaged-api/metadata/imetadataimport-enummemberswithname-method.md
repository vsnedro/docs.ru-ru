---
title: Метод IMetaDataImport::EnumMembersWithName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembersWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type:
- apiref
ms.openlocfilehash: ea451bdd645d2d4dea4c5dd00408e0bc51804803
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492074"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="3d24d-102">Метод IMetaDataImport::EnumMembersWithName</span><span class="sxs-lookup"><span data-stu-id="3d24d-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="3d24d-103">Перечисляет токены MemberDef, представляющие члены указанного типа с заданным именем.</span><span class="sxs-lookup"><span data-stu-id="3d24d-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d24d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d24d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [in]      LPCWSTR     szName,
   [out]     mdToken     rMembers[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d24d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d24d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3d24d-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="3d24d-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="3d24d-107">окне Токен TypeDef, представляющий тип с элементами для перечисления.</span><span class="sxs-lookup"><span data-stu-id="3d24d-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="3d24d-108">окне Имя элемента, ограничивающее область действия перечислителя.</span><span class="sxs-lookup"><span data-stu-id="3d24d-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="3d24d-109">заполняет Массив, используемый для хранения маркеров Мембердеф.</span><span class="sxs-lookup"><span data-stu-id="3d24d-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3d24d-110">[in] Максимальный размер массива `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="3d24d-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="3d24d-111">заполняет Фактическое число токенов Мембердеф, возвращаемых в `rMembers` .</span><span class="sxs-lookup"><span data-stu-id="3d24d-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d24d-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="3d24d-112">Remarks</span></span>  
 <span data-ttu-id="3d24d-113">Этот метод перечисляет поля и методы, но не свойства или события.</span><span class="sxs-lookup"><span data-stu-id="3d24d-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="3d24d-114">В отличие от [IMetaDataImport:: EnumMembers](imetadataimport-enummembers-method.md), `EnumMembersWithName` отменяет все маркеры полей и элементов, у которых нет указанного имени.</span><span class="sxs-lookup"><span data-stu-id="3d24d-114">Unlike [IMetaDataImport::EnumMembers](imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d24d-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3d24d-115">Return Value</span></span>  
  
|<span data-ttu-id="3d24d-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3d24d-116">HRESULT</span></span>|<span data-ttu-id="3d24d-117">Описание</span><span class="sxs-lookup"><span data-stu-id="3d24d-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3d24d-118">`EnumTypeDefs`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="3d24d-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3d24d-119">Нет токенов Мембердеф для перечисления.</span><span class="sxs-lookup"><span data-stu-id="3d24d-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="3d24d-120">В этом случае значение `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="3d24d-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d24d-121">Требования</span><span class="sxs-lookup"><span data-stu-id="3d24d-121">Requirements</span></span>  
 <span data-ttu-id="3d24d-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d24d-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d24d-123">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="3d24d-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3d24d-124">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3d24d-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3d24d-125">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d24d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d24d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="3d24d-126">See also</span></span>

- [<span data-ttu-id="3d24d-127">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="3d24d-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3d24d-128">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="3d24d-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
