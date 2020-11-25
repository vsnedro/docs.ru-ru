---
title: Метод IMetaDataImport::EnumMethodSemantics
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type:
- apiref
ms.openlocfilehash: 3d14aea92633c944d21d867c8152767ae6f1f291
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720975"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="c89e1-102">Метод IMetaDataImport::EnumMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="c89e1-102">IMetaDataImport::EnumMethodSemantics Method</span></span>

<span data-ttu-id="c89e1-103">Перечисляет свойства и события их изменения, с которыми связан указанный метод.</span><span class="sxs-lookup"><span data-stu-id="c89e1-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c89e1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c89e1-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c89e1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c89e1-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="c89e1-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="c89e1-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="c89e1-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="c89e1-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="c89e1-108">окне Токен MethodDef, ограничивающий область перечисления.</span><span class="sxs-lookup"><span data-stu-id="c89e1-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="c89e1-109">заполняет Массив, используемый для хранения событий или свойств.</span><span class="sxs-lookup"><span data-stu-id="c89e1-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c89e1-110">[in] Максимальный размер массива `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="c89e1-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="c89e1-111">заполняет Количество событий или свойств, возвращаемых в `rEventProp` .</span><span class="sxs-lookup"><span data-stu-id="c89e1-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c89e1-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c89e1-112">Return Value</span></span>  
  
|<span data-ttu-id="c89e1-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c89e1-113">HRESULT</span></span>|<span data-ttu-id="c89e1-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c89e1-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c89e1-115">`EnumMethodSemantics` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="c89e1-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c89e1-116">Нет событий или свойств для перечисления.</span><span class="sxs-lookup"><span data-stu-id="c89e1-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="c89e1-117">В этом случае значение `pcEventProp` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="c89e1-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c89e1-118">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c89e1-118">Remarks</span></span>  

 <span data-ttu-id="c89e1-119">Многие типы среды CLR определяют события *свойств* `Changed` и методы `On` *свойств* , `Changed` связанные с их свойствами.</span><span class="sxs-lookup"><span data-stu-id="c89e1-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="c89e1-120">Например, <xref:System.Windows.Forms.Control?displayProperty=nameWithType> тип определяет <xref:System.Windows.Forms.Control.Font%2A> свойство, <xref:System.Windows.Forms.Control.FontChanged> событие и <xref:System.Windows.Forms.Control.OnFontChanged%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="c89e1-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="c89e1-121">Метод доступа set <xref:System.Windows.Forms.Control.Font%2A> свойства вызывает <xref:System.Windows.Forms.Control.OnFontChanged%2A> метод, который, в свою очередь, вызывает <xref:System.Windows.Forms.Control.FontChanged> событие.</span><span class="sxs-lookup"><span data-stu-id="c89e1-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="c89e1-122">`EnumMethodSemantics` <xref:System.Windows.Forms.Control.OnFontChanged%2A> Чтобы получить ссылки на <xref:System.Windows.Forms.Control.Font%2A> свойство и событие, необходимо вызвать метод с помощью MethodDef для <xref:System.Windows.Forms.Control.FontChanged> .</span><span class="sxs-lookup"><span data-stu-id="c89e1-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c89e1-123">Требования</span><span class="sxs-lookup"><span data-stu-id="c89e1-123">Requirements</span></span>  

 <span data-ttu-id="c89e1-124">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c89e1-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c89e1-125">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="c89e1-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c89e1-126">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c89e1-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c89e1-127">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c89e1-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c89e1-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c89e1-128">See also</span></span>

- [<span data-ttu-id="c89e1-129">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c89e1-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c89e1-130">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c89e1-130">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
