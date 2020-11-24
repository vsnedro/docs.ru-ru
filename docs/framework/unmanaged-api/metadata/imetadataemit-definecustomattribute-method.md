---
title: Метод IMetaDataEmit::DefineCustomAttribute
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineCustomAttribute
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type:
- apiref
ms.openlocfilehash: 096a460f9d6581ebdd00f8487af68f652524d52f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681669"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="01476-102">Метод IMetaDataEmit::DefineCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="01476-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>

<span data-ttu-id="01476-103">Создает определение для настраиваемого атрибута с указанной подписью метаданных, присоединяемого к указанному объекту и получает маркер для этого определения настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="01476-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01476-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01476-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (
    [in]  mdToken     tkObj,
    [in]  mdToken     tkType,
    [in]  void const  *pCustomAttribute,
    [in]  ULONG       cbCustomAttribute,
    [out] mdCustomAttribute *pcv
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01476-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="01476-105">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="01476-106">окне Токен для элемента владельца.</span><span class="sxs-lookup"><span data-stu-id="01476-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="01476-107">окне Токен, определяющий настраиваемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="01476-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="01476-108">окне Указатель на настраиваемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="01476-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="01476-109">окне Число байтов в `pCustomAttribute` .</span><span class="sxs-lookup"><span data-stu-id="01476-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="01476-110">заполняет `mdCustomAttribute` Назначенный маркер.</span><span class="sxs-lookup"><span data-stu-id="01476-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01476-111">Требования</span><span class="sxs-lookup"><span data-stu-id="01476-111">Requirements</span></span>  

 <span data-ttu-id="01476-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01476-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01476-113">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="01476-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="01476-114">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="01476-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01476-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01476-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01476-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="01476-116">See also</span></span>

- [<span data-ttu-id="01476-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="01476-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="01476-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="01476-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
