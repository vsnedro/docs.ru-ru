---
title: Метод IMetaDataEmit::DefineUserString
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineUserString
helpviewer_keywords:
- DefineUserString method [.NET Framework metadata]
- IMetaDataEmit::DefineUserString method [.NET Framework metadata]
ms.assetid: 88fb7ef3-bbdf-429c-b678-c9c153456461
topic_type:
- apiref
ms.openlocfilehash: def77bb64e21b1421983cf263d488ecc1ddb9452
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009329"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="24f00-102">Метод IMetaDataEmit::DefineUserString</span><span class="sxs-lookup"><span data-stu-id="24f00-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="24f00-103">Возвращает токен метаданных для указанной литеральной строки.</span><span class="sxs-lookup"><span data-stu-id="24f00-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24f00-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24f00-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineUserString (
    [in]  LPCWSTR     szString,
    [in]  ULONG       cchString,
    [out] mdString    *pstk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24f00-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="24f00-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="24f00-106">окне Пользовательская строка для хранения.</span><span class="sxs-lookup"><span data-stu-id="24f00-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="24f00-107">окне Число расширенных символов в `szString` .</span><span class="sxs-lookup"><span data-stu-id="24f00-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="24f00-108">заполняет Назначенный токен строки.</span><span class="sxs-lookup"><span data-stu-id="24f00-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24f00-109">Требования</span><span class="sxs-lookup"><span data-stu-id="24f00-109">Requirements</span></span>  
 <span data-ttu-id="24f00-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24f00-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24f00-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="24f00-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="24f00-112">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="24f00-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24f00-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24f00-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24f00-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="24f00-114">See also</span></span>

- [<span data-ttu-id="24f00-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="24f00-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="24f00-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="24f00-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
