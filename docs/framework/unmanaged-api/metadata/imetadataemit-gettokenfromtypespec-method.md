---
title: Метод IMetaDataEmit::GetTokenFromTypeSpec
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
ms.openlocfilehash: 3a8f369728b8464850259518981bf6690cb17a01
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722042"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="9991e-102">Метод IMetaDataEmit::GetTokenFromTypeSpec</span><span class="sxs-lookup"><span data-stu-id="9991e-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>

<span data-ttu-id="9991e-103">Возвращает токен метаданных для типа с указанной сигнатурой метаданных.</span><span class="sxs-lookup"><span data-stu-id="9991e-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9991e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9991e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (
    [in]  PCCOR_SIGNATURE       pvSig,
    [in]  ULONG                 cbSig,
    [out] mdTypeSpec            *ptypespec
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9991e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9991e-105">Parameters</span></span>  

 `pvSig`  
 <span data-ttu-id="9991e-106">окне Определяемая сигнатура.</span><span class="sxs-lookup"><span data-stu-id="9991e-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="9991e-107">окне Число байтов в `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="9991e-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="9991e-108">заполняет `mdTypeSpec` Назначенный маркер.</span><span class="sxs-lookup"><span data-stu-id="9991e-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9991e-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9991e-109">Requirements</span></span>  

 <span data-ttu-id="9991e-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9991e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9991e-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="9991e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9991e-112">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9991e-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9991e-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9991e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9991e-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9991e-114">See also</span></span>

- [<span data-ttu-id="9991e-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="9991e-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="9991e-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="9991e-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
