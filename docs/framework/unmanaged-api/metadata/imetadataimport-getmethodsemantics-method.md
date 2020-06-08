---
title: Метод IMetaDataImport::GetMethodSemantics
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
ms.openlocfilehash: 2cfb66203d8f2d69ea188f6913a5ef34dd74791e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503605"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="785ee-102">Метод IMetaDataImport::GetMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="785ee-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="785ee-103">Получает флаги, указывающие связь между методом, на который ссылается указанный токен MethodDef, и связанным свойством и событием, на которые ссылается указанный токен Евентпроп.</span><span class="sxs-lookup"><span data-stu-id="785ee-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="785ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="785ee-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="785ee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="785ee-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="785ee-106">окне Токен MethodDef, представляющий метод, для которого необходимо получить сведения о семантической роли.</span><span class="sxs-lookup"><span data-stu-id="785ee-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="785ee-107">окне Токен, представляющий парное свойство и событие, для которого необходимо получить роль метода.</span><span class="sxs-lookup"><span data-stu-id="785ee-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="785ee-108">заполняет Указатель на соответствующие флаги семантики.</span><span class="sxs-lookup"><span data-stu-id="785ee-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="785ee-109">Это значение является битовой маской из перечисления [кормесодсемантиксаттр](cormethodsemanticsattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="785ee-109">This value is a bitmask from the [CorMethodSemanticsAttr](cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="785ee-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="785ee-110">Remarks</span></span>  
 <span data-ttu-id="785ee-111">Метод [IMetaDataEmit::D ефинепроперти](imetadataemit-defineproperty-method.md) задает флаги семантики метода.</span><span class="sxs-lookup"><span data-stu-id="785ee-111">The [IMetaDataEmit::DefineProperty](imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="785ee-112">Требования</span><span class="sxs-lookup"><span data-stu-id="785ee-112">Requirements</span></span>  
 <span data-ttu-id="785ee-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="785ee-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="785ee-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="785ee-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="785ee-115">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="785ee-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="785ee-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="785ee-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="785ee-117">См. также</span><span class="sxs-lookup"><span data-stu-id="785ee-117">See also</span></span>

- [<span data-ttu-id="785ee-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="785ee-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="785ee-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="785ee-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
