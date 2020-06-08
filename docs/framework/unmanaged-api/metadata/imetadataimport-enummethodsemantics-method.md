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
ms.openlocfilehash: 213cbd955e3d47a49abde579a54af48641e225ec
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491931"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="b2f2a-102">Метод IMetaDataImport::EnumMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="b2f2a-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="b2f2a-103">Перечисляет свойства и события их изменения, с которыми связан указанный метод.</span><span class="sxs-lookup"><span data-stu-id="b2f2a-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2f2a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2f2a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2f2a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2f2a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b2f2a-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="b2f2a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b2f2a-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="b2f2a-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="b2f2a-108">окне Токен MethodDef, ограничивающий область перечисления.</span><span class="sxs-lookup"><span data-stu-id="b2f2a-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="b2f2a-109">заполняет Массив, используемый для хранения событий или свойств.</span><span class="sxs-lookup"><span data-stu-id="b2f2a-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b2f2a-110">[in] Максимальный размер массива `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="b2f2a-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="b2f2a-111">заполняет Количество событий или свойств, возвращаемых в `rEventProp` .</span><span class="sxs-lookup"><span data-stu-id="b2f2a-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2f2a-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b2f2a-112">Return Value</span></span>  
  
|<span data-ttu-id="b2f2a-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2f2a-113">HRESULT</span></span>|<span data-ttu-id="b2f2a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b2f2a-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b2f2a-115">`EnumMethodSemantics`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="b2f2a-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b2f2a-116">Нет событий или свойств для перечисления.</span><span class="sxs-lookup"><span data-stu-id="b2f2a-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="b2f2a-117">В этом случае значение `pcEventProp` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="b2f2a-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2f2a-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2f2a-118">Remarks</span></span>  
 <span data-ttu-id="b2f2a-119">Многие типы среды CLR определяют события *свойств* `Changed` и методы `On` *свойств* , `Changed` связанные с их свойствами.</span><span class="sxs-lookup"><span data-stu-id="b2f2a-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="b2f2a-120">Например, <xref:System.Windows.Forms.Control?displayProperty=nameWithType> тип определяет <xref:System.Windows.Forms.Control.Font%2A> свойство, <xref:System.Windows.Forms.Control.FontChanged> событие и <xref:System.Windows.Forms.Control.OnFontChanged%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="b2f2a-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="b2f2a-121">Метод доступа set <xref:System.Windows.Forms.Control.Font%2A> свойства вызывает <xref:System.Windows.Forms.Control.OnFontChanged%2A> метод, который, в свою очередь, вызывает <xref:System.Windows.Forms.Control.FontChanged> событие.</span><span class="sxs-lookup"><span data-stu-id="b2f2a-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="b2f2a-122">`EnumMethodSemantics` <xref:System.Windows.Forms.Control.OnFontChanged%2A> Чтобы получить ссылки на <xref:System.Windows.Forms.Control.Font%2A> свойство и событие, необходимо вызвать метод с помощью MethodDef для <xref:System.Windows.Forms.Control.FontChanged> .</span><span class="sxs-lookup"><span data-stu-id="b2f2a-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2f2a-123">Требования</span><span class="sxs-lookup"><span data-stu-id="b2f2a-123">Requirements</span></span>  
 <span data-ttu-id="b2f2a-124">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2f2a-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2f2a-125">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="b2f2a-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b2f2a-126">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b2f2a-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b2f2a-127">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2f2a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2f2a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="b2f2a-128">See also</span></span>

- [<span data-ttu-id="b2f2a-129">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b2f2a-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="b2f2a-130">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b2f2a-130">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
