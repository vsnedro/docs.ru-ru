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
ms.openlocfilehash: c991c0af845bc6825db6b3bf258fe0809d5db804
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503703"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="59930-102">Метод IMetaDataImport::EnumUnresolvedMethods</span><span class="sxs-lookup"><span data-stu-id="59930-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>
<span data-ttu-id="59930-103">Перечисляет токены MemberDef, представляющие неразрешенные методы в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="59930-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59930-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59930-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59930-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="59930-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="59930-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="59930-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="59930-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="59930-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="59930-108">заполняет Массив, используемый для хранения маркеров Мембердеф.</span><span class="sxs-lookup"><span data-stu-id="59930-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="59930-109">[in] Максимальный размер массива `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="59930-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="59930-110">заполняет Число токенов Мембердеф, возвращаемых в `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="59930-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59930-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="59930-111">Return Value</span></span>  
  
|<span data-ttu-id="59930-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="59930-112">HRESULT</span></span>|<span data-ttu-id="59930-113">Описание</span><span class="sxs-lookup"><span data-stu-id="59930-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="59930-114">`EnumUnresolvedMethods`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="59930-114">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="59930-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="59930-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="59930-116">В этом случае значение `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="59930-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59930-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="59930-117">Remarks</span></span>  
 <span data-ttu-id="59930-118">Неразрешенный метод — это тот, который был объявлен, но не реализован.</span><span class="sxs-lookup"><span data-stu-id="59930-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="59930-119">Метод включается в перечисление, если метод помечен `miForwardRef` , а либо `mdPinvokeImpl` либо `miRuntime` имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="59930-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="59930-120">Иными словами, неразрешенный метод — это метод класса, который помечен, `miForwardRef` но не реализован в неуправляемом коде (достигается через PInvoke) и не реализуется внутри самой среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="59930-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="59930-121">Перечисление исключает все методы, определенные либо в области видимости модуля (Globals), либо в интерфейсах или в абстрактных классах.</span><span class="sxs-lookup"><span data-stu-id="59930-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59930-122">Требования</span><span class="sxs-lookup"><span data-stu-id="59930-122">Requirements</span></span>  
 <span data-ttu-id="59930-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59930-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59930-124">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="59930-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="59930-125">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="59930-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="59930-126">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59930-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59930-127">См. также</span><span class="sxs-lookup"><span data-stu-id="59930-127">See also</span></span>

- [<span data-ttu-id="59930-128">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="59930-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="59930-129">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="59930-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
