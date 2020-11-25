---
title: Метод IMetaDataImport::EnumUserStrings
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUserStrings
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type:
- apiref
ms.openlocfilehash: c7dcc740dcf9b228713693a57dc8ef96d215ebad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716568"
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="46fe9-102">Метод IMetaDataImport::EnumUserStrings</span><span class="sxs-lookup"><span data-stu-id="46fe9-102">IMetaDataImport::EnumUserStrings Method</span></span>

<span data-ttu-id="46fe9-103">Перечисляет токены String, представляющие жестко заданные строки в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="46fe9-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46fe9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46fe9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46fe9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="46fe9-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="46fe9-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="46fe9-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="46fe9-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="46fe9-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="46fe9-108">заполняет Массив, используемый для хранения токенов строк.</span><span class="sxs-lookup"><span data-stu-id="46fe9-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="46fe9-109">[in] Максимальный размер массива `rStrings`.</span><span class="sxs-lookup"><span data-stu-id="46fe9-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="46fe9-110">заполняет Число токенов строк, возвращаемых в `rStrings` .</span><span class="sxs-lookup"><span data-stu-id="46fe9-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46fe9-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="46fe9-111">Return Value</span></span>  
  
|<span data-ttu-id="46fe9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="46fe9-112">HRESULT</span></span>|<span data-ttu-id="46fe9-113">Описание</span><span class="sxs-lookup"><span data-stu-id="46fe9-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="46fe9-114">`EnumUserStrings` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="46fe9-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="46fe9-115">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="46fe9-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="46fe9-116">В этом случае значение `pcStrings` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="46fe9-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46fe9-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="46fe9-117">Remarks</span></span>  

 <span data-ttu-id="46fe9-118">Строковые токены создаются методом [IMetaDataEmit::D ефинеусерстринг](imetadataemit-defineuserstring-method.md) .</span><span class="sxs-lookup"><span data-stu-id="46fe9-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="46fe9-119">Этот метод предназначен для использования обозревателем метаданных, а не компилятором.</span><span class="sxs-lookup"><span data-stu-id="46fe9-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46fe9-120">Требования</span><span class="sxs-lookup"><span data-stu-id="46fe9-120">Requirements</span></span>  

 <span data-ttu-id="46fe9-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46fe9-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46fe9-122">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="46fe9-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="46fe9-123">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="46fe9-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="46fe9-124">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46fe9-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46fe9-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="46fe9-125">See also</span></span>

- [<span data-ttu-id="46fe9-126">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="46fe9-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="46fe9-127">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="46fe9-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
