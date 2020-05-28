---
title: Метод IMetaDataDispenserEx::GetOption
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type:
- apiref
ms.openlocfilehash: 832adacac4a6df9ccf21578538a1c557150f3ba1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008785"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="8bfc9-102">Метод IMetaDataDispenserEx::GetOption</span><span class="sxs-lookup"><span data-stu-id="8bfc9-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="8bfc9-103">Возвращает значение указанного параметра для текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="8bfc9-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="8bfc9-104">Параметр определяет, как обрабатываются вызовы к текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="8bfc9-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bfc9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8bfc9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bfc9-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8bfc9-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="8bfc9-107">окне Указатель на идентификатор GUID, указывающий параметр, который необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="8bfc9-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="8bfc9-108">Список поддерживаемых идентификаторов GUID см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="8bfc9-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="8bfc9-109">заполняет Значение возвращаемого параметра.</span><span class="sxs-lookup"><span data-stu-id="8bfc9-109">[out] The value of the returned option.</span></span> <span data-ttu-id="8bfc9-110">Тип этого значения будет представлять собой вариант типа указанного параметра.</span><span class="sxs-lookup"><span data-stu-id="8bfc9-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bfc9-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="8bfc9-111">Remarks</span></span>  
 <span data-ttu-id="8bfc9-112">В следующем списке показаны идентификаторы GUID, которые поддерживаются для этого метода.</span><span class="sxs-lookup"><span data-stu-id="8bfc9-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="8bfc9-113">Описание см. в описании метода [IMetaDataDispenserEx:: SetOption](imetadatadispenserex-setoption-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8bfc9-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="8bfc9-114">Если `optionId` не находится в этом списке, этот метод возвращает значение HRESULT `E_INVALIDARG` , указывающее на неверный параметр.</span><span class="sxs-lookup"><span data-stu-id="8bfc9-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="8bfc9-115">метадатачеккдупликатесфор</span><span class="sxs-lookup"><span data-stu-id="8bfc9-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="8bfc9-116">метадатарефтодефчекк</span><span class="sxs-lookup"><span data-stu-id="8bfc9-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="8bfc9-117">метадатанотификатионфортокенмовемент</span><span class="sxs-lookup"><span data-stu-id="8bfc9-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="8bfc9-118">метадатасетенк</span><span class="sxs-lookup"><span data-stu-id="8bfc9-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="8bfc9-119">метадатаеррорифемитаутофордер</span><span class="sxs-lookup"><span data-stu-id="8bfc9-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="8bfc9-120">метадатаженератетцеадаптерс</span><span class="sxs-lookup"><span data-stu-id="8bfc9-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="8bfc9-121">метадаталинкероптионс</span><span class="sxs-lookup"><span data-stu-id="8bfc9-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bfc9-122">Требования</span><span class="sxs-lookup"><span data-stu-id="8bfc9-122">Requirements</span></span>  
 <span data-ttu-id="8bfc9-123">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bfc9-123">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bfc9-124">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="8bfc9-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8bfc9-125">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8bfc9-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8bfc9-126">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bfc9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bfc9-127">См. также статью</span><span class="sxs-lookup"><span data-stu-id="8bfc9-127">See also</span></span>

- [<span data-ttu-id="8bfc9-128">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="8bfc9-128">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="8bfc9-129">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="8bfc9-129">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
