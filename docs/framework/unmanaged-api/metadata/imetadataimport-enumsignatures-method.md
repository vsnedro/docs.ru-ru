---
title: Метод IMetaDataImport::EnumSignatures
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumSignatures
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type:
- apiref
ms.openlocfilehash: 3021124184ab0491337a07144e6f77b5bfea3681
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721976"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="997c2-102">Метод IMetaDataImport::EnumSignatures</span><span class="sxs-lookup"><span data-stu-id="997c2-102">IMetaDataImport::EnumSignatures Method</span></span>

<span data-ttu-id="997c2-103">Перечисляет токены Signature, представляющие отдельные подписи в текущей области.</span><span class="sxs-lookup"><span data-stu-id="997c2-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="997c2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="997c2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="997c2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="997c2-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="997c2-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="997c2-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="997c2-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="997c2-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="997c2-108">заполняет Массив, используемый для хранения маркеров подписи.</span><span class="sxs-lookup"><span data-stu-id="997c2-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="997c2-109">[in] Максимальный размер массива `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="997c2-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="997c2-110">заполняет Число маркеров подписи, возвращаемых в `rSignatures` .</span><span class="sxs-lookup"><span data-stu-id="997c2-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="997c2-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="997c2-111">Return Value</span></span>  
  
|<span data-ttu-id="997c2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="997c2-112">HRESULT</span></span>|<span data-ttu-id="997c2-113">Описание</span><span class="sxs-lookup"><span data-stu-id="997c2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="997c2-114">`EnumSignatures` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="997c2-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="997c2-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="997c2-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="997c2-116">В этом случае значение `pcSignatures` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="997c2-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="997c2-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="997c2-117">Remarks</span></span>  

 <span data-ttu-id="997c2-118">Маркеры подписи создаются методом [IMetaDataEmit:: жеттокенфромсиг](imetadataemit-gettokenfromsig-method.md) .</span><span class="sxs-lookup"><span data-stu-id="997c2-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="997c2-119">Требования</span><span class="sxs-lookup"><span data-stu-id="997c2-119">Requirements</span></span>  

 <span data-ttu-id="997c2-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="997c2-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="997c2-121">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="997c2-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="997c2-122">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="997c2-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="997c2-123">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="997c2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="997c2-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="997c2-124">See also</span></span>

- [<span data-ttu-id="997c2-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="997c2-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="997c2-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="997c2-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
