---
title: Метод IMetaDataImport::EnumParams
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumParams
helpviewer_keywords:
- IMetaDataImport::EnumParams method [.NET Framework metadata]
- EnumParams method [.NET Framework metadata]
ms.assetid: 52118dc9-fe6e-4b39-aa48-c3cc3ea4214d
topic_type:
- apiref
ms.openlocfilehash: b41f9bb05a43ac4c6dd8a89c45ef4826741e5679
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728268"
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="66a33-102">Метод IMetaDataImport::EnumParams</span><span class="sxs-lookup"><span data-stu-id="66a33-102">IMetaDataImport::EnumParams Method</span></span>

<span data-ttu-id="66a33-103">Перечисляет токены ParamDef, представляющие параметры метода, на который ссылается указанный токен MethodDef.</span><span class="sxs-lookup"><span data-stu-id="66a33-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66a33-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66a33-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66a33-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="66a33-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="66a33-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="66a33-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="66a33-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="66a33-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="66a33-108">окне Токен MethodDef, представляющий метод с параметрами для перечисления.</span><span class="sxs-lookup"><span data-stu-id="66a33-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="66a33-109">заполняет Массив, используемый для хранения маркеров Парамдеф.</span><span class="sxs-lookup"><span data-stu-id="66a33-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="66a33-110">[in] Максимальный размер массива `rParams`.</span><span class="sxs-lookup"><span data-stu-id="66a33-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="66a33-111">заполняет Число токенов Парамдеф, возвращаемых в `rParams` .</span><span class="sxs-lookup"><span data-stu-id="66a33-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66a33-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="66a33-112">Return Value</span></span>  
  
|<span data-ttu-id="66a33-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="66a33-113">HRESULT</span></span>|<span data-ttu-id="66a33-114">Описание</span><span class="sxs-lookup"><span data-stu-id="66a33-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="66a33-115">`EnumParams` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="66a33-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="66a33-116">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="66a33-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="66a33-117">В этом случае значение `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="66a33-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="66a33-118">Требования</span><span class="sxs-lookup"><span data-stu-id="66a33-118">Requirements</span></span>  

 <span data-ttu-id="66a33-119">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66a33-119">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66a33-120">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="66a33-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="66a33-121">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="66a33-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="66a33-122">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66a33-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66a33-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="66a33-123">See also</span></span>

- [<span data-ttu-id="66a33-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="66a33-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="66a33-125">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="66a33-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
