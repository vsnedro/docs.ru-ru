---
title: Метод IMetaDataImport::EnumMethods
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
ms.openlocfilehash: 00726b7e74bdedc658886cccbc4329eaf3ae76d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696808"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="a24e3-102">Метод IMetaDataImport::EnumMethods</span><span class="sxs-lookup"><span data-stu-id="a24e3-102">IMetaDataImport::EnumMethods Method</span></span>

<span data-ttu-id="a24e3-103">Перечисляет токены MethodDef, представляющие методы указанного типа.</span><span class="sxs-lookup"><span data-stu-id="a24e3-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a24e3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a24e3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,
   [in]  mdTypeDef      cl,
   [out] mdMethodDef    rMethods[],
   [in]  ULONG          cMax,
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a24e3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a24e3-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="a24e3-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="a24e3-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a24e3-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="a24e3-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="a24e3-108">окне Токен TypeDef, представляющий тип с методами для перечисления.</span><span class="sxs-lookup"><span data-stu-id="a24e3-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="a24e3-109">заполняет Массив для хранения токенов MethodDef.</span><span class="sxs-lookup"><span data-stu-id="a24e3-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a24e3-110">окне Максимальный размер `rMethods` массива MethodDef.</span><span class="sxs-lookup"><span data-stu-id="a24e3-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a24e3-111">заполняет Число токенов MethodDef, возвращаемых в `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="a24e3-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a24e3-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a24e3-112">Return Value</span></span>  
  
|<span data-ttu-id="a24e3-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a24e3-113">HRESULT</span></span>|<span data-ttu-id="a24e3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a24e3-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a24e3-115">`EnumMethods` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="a24e3-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a24e3-116">Отсутствуют токены MethodDef для перечисления.</span><span class="sxs-lookup"><span data-stu-id="a24e3-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="a24e3-117">В этом случае значение `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="a24e3-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a24e3-118">Требования</span><span class="sxs-lookup"><span data-stu-id="a24e3-118">Requirements</span></span>  

 <span data-ttu-id="a24e3-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a24e3-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a24e3-120">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="a24e3-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a24e3-121">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a24e3-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a24e3-122">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a24e3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a24e3-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a24e3-123">See also</span></span>

- [<span data-ttu-id="a24e3-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a24e3-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a24e3-125">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a24e3-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
