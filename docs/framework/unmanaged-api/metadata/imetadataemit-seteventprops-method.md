---
title: Метод IMetaDataEmit::SetEventProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type:
- apiref
ms.openlocfilehash: 720133e64c02aa09c9ff7e43a20630b0d55c1acf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008759"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="05955-102">Метод IMetaDataEmit::SetEventProps</span><span class="sxs-lookup"><span data-stu-id="05955-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="05955-103">Задает или обновляет указанную функцию события, определенного при предыдущем вызове метода [IMetaDataEmit::D ефинивент](imetadataemit-defineevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="05955-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05955-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05955-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEventProps (  
    [in]  mdEvent     ev,
    [in]  DWORD       dwEventFlags,
    [in]  mdToken     tkEventType,
    [in]  mdMethodDef mdAddOn,
    [in]  mdMethodDef mdRemoveOn,
    [in]  mdMethodDef mdFire,
    [in]  mdMethodDef rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05955-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="05955-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="05955-106">окне Токен события.</span><span class="sxs-lookup"><span data-stu-id="05955-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="05955-107">окне Флаги событий.</span><span class="sxs-lookup"><span data-stu-id="05955-107">[in] Event flags.</span></span> <span data-ttu-id="05955-108">Это битовая маска `CorEventAttr` значений.</span><span class="sxs-lookup"><span data-stu-id="05955-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="05955-109">окне Токен для класса событий.</span><span class="sxs-lookup"><span data-stu-id="05955-109">[in] The token for the event class.</span></span> <span data-ttu-id="05955-110">Это либо маркер, либо `mdTypeDef` `mdTypeRef` .</span><span class="sxs-lookup"><span data-stu-id="05955-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="05955-111">окне Метод, используемый для подписки на событие, или значение null.</span><span class="sxs-lookup"><span data-stu-id="05955-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="05955-112">окне Метод, используемый для отмены подписки на событие или значение null.</span><span class="sxs-lookup"><span data-stu-id="05955-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="05955-113">окне Метод, используемый (производным классом) для вызова события.</span><span class="sxs-lookup"><span data-stu-id="05955-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="05955-114">окне Массив токенов для других методов, связанных с событием.</span><span class="sxs-lookup"><span data-stu-id="05955-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="05955-115">Последний элемент массива должен быть `mdMethodDefNil` .</span><span class="sxs-lookup"><span data-stu-id="05955-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05955-116">Требования</span><span class="sxs-lookup"><span data-stu-id="05955-116">Requirements</span></span>  
 <span data-ttu-id="05955-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05955-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05955-118">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="05955-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="05955-119">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="05955-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05955-120">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05955-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05955-121">См. также статью</span><span class="sxs-lookup"><span data-stu-id="05955-121">See also</span></span>

- [<span data-ttu-id="05955-122">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="05955-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="05955-123">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="05955-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
