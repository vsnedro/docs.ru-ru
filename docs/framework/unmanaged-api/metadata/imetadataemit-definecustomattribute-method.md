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
ms.openlocfilehash: 17757df566ba8d141e7adec00dcc1f75959d0e00
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005633"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="6c9be-102">Метод IMetaDataEmit::DefineCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="6c9be-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="6c9be-103">Создает определение для настраиваемого атрибута с указанной подписью метаданных, присоединяемого к указанному объекту и получает маркер для этого определения настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="6c9be-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c9be-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c9be-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (
    [in]  mdToken     tkObj,
    [in]  mdToken     tkType,
    [in]  void const  *pCustomAttribute,
    [in]  ULONG       cbCustomAttribute,
    [out] mdCustomAttribute *pcv
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c9be-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6c9be-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="6c9be-106">окне Токен для элемента владельца.</span><span class="sxs-lookup"><span data-stu-id="6c9be-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="6c9be-107">окне Токен, определяющий настраиваемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="6c9be-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="6c9be-108">окне Указатель на настраиваемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="6c9be-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="6c9be-109">окне Число байтов в `pCustomAttribute` .</span><span class="sxs-lookup"><span data-stu-id="6c9be-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="6c9be-110">заполняет `mdCustomAttribute`Назначенный маркер.</span><span class="sxs-lookup"><span data-stu-id="6c9be-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c9be-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6c9be-111">Requirements</span></span>  
 <span data-ttu-id="6c9be-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c9be-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c9be-113">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="6c9be-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6c9be-114">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6c9be-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c9be-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c9be-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c9be-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="6c9be-116">See also</span></span>

- [<span data-ttu-id="6c9be-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="6c9be-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="6c9be-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="6c9be-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
