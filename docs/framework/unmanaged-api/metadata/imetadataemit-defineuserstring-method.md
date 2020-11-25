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
ms.openlocfilehash: ed3c20fe8272ca3205079d26df0b7bde12e58307
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732701"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="d2e63-102">Метод IMetaDataEmit::DefineUserString</span><span class="sxs-lookup"><span data-stu-id="d2e63-102">IMetaDataEmit::DefineUserString Method</span></span>

<span data-ttu-id="d2e63-103">Возвращает токен метаданных для указанной литеральной строки.</span><span class="sxs-lookup"><span data-stu-id="d2e63-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2e63-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d2e63-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineUserString (
    [in]  LPCWSTR     szString,
    [in]  ULONG       cchString,
    [out] mdString    *pstk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2e63-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d2e63-105">Parameters</span></span>  

 `szString`  
 <span data-ttu-id="d2e63-106">окне Пользовательская строка для хранения.</span><span class="sxs-lookup"><span data-stu-id="d2e63-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="d2e63-107">окне Число расширенных символов в `szString` .</span><span class="sxs-lookup"><span data-stu-id="d2e63-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="d2e63-108">заполняет Назначенный токен строки.</span><span class="sxs-lookup"><span data-stu-id="d2e63-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2e63-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d2e63-109">Requirements</span></span>  

 <span data-ttu-id="d2e63-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2e63-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2e63-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="d2e63-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2e63-112">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d2e63-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2e63-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2e63-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2e63-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d2e63-114">See also</span></span>

- [<span data-ttu-id="d2e63-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="d2e63-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="d2e63-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="d2e63-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
