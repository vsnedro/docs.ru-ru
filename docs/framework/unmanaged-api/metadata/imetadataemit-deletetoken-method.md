---
title: Метод IMetaDataEmit::DeleteToken
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteToken
helpviewer_keywords:
- DeleteToken method [.NET Framework metadata]
- IMetaDataEmit::DeleteToken method [.NET Framework metadata]
ms.assetid: a4926d0a-261b-46b1-9994-82633661a64b
topic_type:
- apiref
ms.openlocfilehash: eaa465855c9e933286bcdd189e62048510088ec7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722080"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="3847c-102">Метод IMetaDataEmit::DeleteToken</span><span class="sxs-lookup"><span data-stu-id="3847c-102">IMetaDataEmit::DeleteToken Method</span></span>

<span data-ttu-id="3847c-103">Удаляет указанный токен из текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="3847c-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3847c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3847c-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteToken (
    [in]  mdToken     tkObj
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3847c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3847c-105">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="3847c-106">окне Удаляемый токен.</span><span class="sxs-lookup"><span data-stu-id="3847c-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3847c-107">Требования</span><span class="sxs-lookup"><span data-stu-id="3847c-107">Requirements</span></span>  

 <span data-ttu-id="3847c-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3847c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3847c-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="3847c-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3847c-110">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3847c-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3847c-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3847c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3847c-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3847c-112">See also</span></span>

- [<span data-ttu-id="3847c-113">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="3847c-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="3847c-114">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="3847c-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
