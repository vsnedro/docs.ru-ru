---
title: Метод IMetaDataEmit::GetTokenFromSig
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromSig
helpviewer_keywords:
- IMetaDataEmit::GetTokenFromSig method [.NET Framework metadata]
- GetTokenFromSig method [.NET Framework metadata]
ms.assetid: 50a58a83-6287-40a4-b315-47823cea0a5c
topic_type:
- apiref
ms.openlocfilehash: b41891227d94b66bf59128d620eba9da117fe92a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722054"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="bee21-102">Метод IMetaDataEmit::GetTokenFromSig</span><span class="sxs-lookup"><span data-stu-id="bee21-102">IMetaDataEmit::GetTokenFromSig Method</span></span>

<span data-ttu-id="bee21-103">Возвращает токен для указанной сигнатуры метаданных.</span><span class="sxs-lookup"><span data-stu-id="bee21-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bee21-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bee21-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (
    [in]  PCCOR_SIGNATURE pvSig,
    [in]  ULONG       cbSig,
    [out] mdSignature *pmsig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bee21-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bee21-105">Parameters</span></span>  

 `pvSig`  
 <span data-ttu-id="bee21-106">окне Сохраняемая и хранимая сигнатура.</span><span class="sxs-lookup"><span data-stu-id="bee21-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="bee21-107">окне Число байтов в `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="bee21-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="bee21-108">заполняет `mdSignature` Назначенный маркер.</span><span class="sxs-lookup"><span data-stu-id="bee21-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bee21-109">Требования</span><span class="sxs-lookup"><span data-stu-id="bee21-109">Requirements</span></span>  

 <span data-ttu-id="bee21-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bee21-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bee21-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="bee21-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bee21-112">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bee21-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bee21-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bee21-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bee21-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bee21-114">See also</span></span>

- [<span data-ttu-id="bee21-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="bee21-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="bee21-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="bee21-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
