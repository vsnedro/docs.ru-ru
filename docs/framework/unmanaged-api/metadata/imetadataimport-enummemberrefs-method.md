---
title: Метод IMetaDataImport::EnumMemberRefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMemberRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type:
- apiref
ms.openlocfilehash: d8b02e85efc2cd7364690dd42104a313ba6ec272
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711459"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="4679e-102">Метод IMetaDataImport::EnumMemberRefs</span><span class="sxs-lookup"><span data-stu-id="4679e-102">IMetaDataImport::EnumMemberRefs Method</span></span>

<span data-ttu-id="4679e-103">Перечисляет токены MemberRef, представляющие члены указанного типа.</span><span class="sxs-lookup"><span data-stu-id="4679e-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4679e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4679e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,
   [in]   mdToken        tkParent,
   [out]  mdMemberRef    rMemberRefs[],
   [in]   ULONG          cMax,
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4679e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4679e-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="4679e-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="4679e-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="4679e-107">окне Токен TypeDef, TypeRef, MethodDef или ModuleRef для типа, элементы которого необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="4679e-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="4679e-108">заполняет Массив, используемый для хранения токенов MemberRef.</span><span class="sxs-lookup"><span data-stu-id="4679e-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4679e-109">[in] Максимальный размер массива `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="4679e-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="4679e-110">заполняет Фактическое число токенов MemberRef, возвращаемых в `rMemberRefs` .</span><span class="sxs-lookup"><span data-stu-id="4679e-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4679e-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4679e-111">Return Value</span></span>  
  
|<span data-ttu-id="4679e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4679e-112">HRESULT</span></span>|<span data-ttu-id="4679e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4679e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4679e-114">`EnumMemberRefs` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="4679e-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4679e-115">Отсутствуют токены MemberRef для перечисления.</span><span class="sxs-lookup"><span data-stu-id="4679e-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="4679e-116">В этом случае значение `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="4679e-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4679e-117">Требования</span><span class="sxs-lookup"><span data-stu-id="4679e-117">Requirements</span></span>  

 <span data-ttu-id="4679e-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4679e-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4679e-119">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="4679e-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4679e-120">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4679e-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4679e-121">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4679e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4679e-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4679e-122">See also</span></span>

- [<span data-ttu-id="4679e-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="4679e-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="4679e-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="4679e-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
