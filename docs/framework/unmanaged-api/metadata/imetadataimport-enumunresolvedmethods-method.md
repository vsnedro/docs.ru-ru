---
title: Метод IMetaDataImport::EnumUnresolvedMethods
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUnresolvedMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type:
- apiref
ms.openlocfilehash: 6b5e7bbe2303a200d7829fea12e228a513595f97
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716558"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="12c7c-102">Метод IMetaDataImport::EnumUnresolvedMethods</span><span class="sxs-lookup"><span data-stu-id="12c7c-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>

<span data-ttu-id="12c7c-103">Перечисляет токены MemberDef, представляющие неразрешенные методы в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="12c7c-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12c7c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12c7c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12c7c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="12c7c-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="12c7c-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="12c7c-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="12c7c-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="12c7c-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="12c7c-108">заполняет Массив, используемый для хранения маркеров Мембердеф.</span><span class="sxs-lookup"><span data-stu-id="12c7c-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="12c7c-109">[in] Максимальный размер массива `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="12c7c-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="12c7c-110">заполняет Число токенов Мембердеф, возвращаемых в `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="12c7c-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12c7c-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="12c7c-111">Return Value</span></span>  
  
|<span data-ttu-id="12c7c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="12c7c-112">HRESULT</span></span>|<span data-ttu-id="12c7c-113">Описание</span><span class="sxs-lookup"><span data-stu-id="12c7c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="12c7c-114">`EnumUnresolvedMethods` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="12c7c-114">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="12c7c-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="12c7c-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="12c7c-116">В этом случае значение `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="12c7c-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12c7c-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="12c7c-117">Remarks</span></span>  

 <span data-ttu-id="12c7c-118">Неразрешенный метод — это тот, который был объявлен, но не реализован.</span><span class="sxs-lookup"><span data-stu-id="12c7c-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="12c7c-119">Метод включается в перечисление, если метод помечен `miForwardRef` , а либо `mdPinvokeImpl` либо `miRuntime` имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="12c7c-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="12c7c-120">Иными словами, неразрешенный метод — это метод класса, который помечен, `miForwardRef` но не реализован в неуправляемом коде (достигается через PInvoke) и не реализуется внутри самой среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="12c7c-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="12c7c-121">Перечисление исключает все методы, определенные либо в области видимости модуля (Globals), либо в интерфейсах или в абстрактных классах.</span><span class="sxs-lookup"><span data-stu-id="12c7c-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12c7c-122">Требования</span><span class="sxs-lookup"><span data-stu-id="12c7c-122">Requirements</span></span>  

 <span data-ttu-id="12c7c-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12c7c-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12c7c-124">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="12c7c-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="12c7c-125">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="12c7c-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="12c7c-126">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12c7c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12c7c-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="12c7c-127">See also</span></span>

- [<span data-ttu-id="12c7c-128">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="12c7c-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="12c7c-129">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="12c7c-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
