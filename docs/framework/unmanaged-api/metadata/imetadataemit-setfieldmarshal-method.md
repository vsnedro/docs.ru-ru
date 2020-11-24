---
title: Метод IMetaDataEmit::SetFieldMarshal
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type:
- apiref
ms.openlocfilehash: d479416f5f1cb4042f9b3fc112e22b67e37d3f78
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672712"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="90aea-102">Метод IMetaDataEmit::SetFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="90aea-102">IMetaDataEmit::SetFieldMarshal Method</span></span>

<span data-ttu-id="90aea-103">Задает сведения о маршалировании PInvoke для поля, возвращаемого метода или параметра метода, на который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="90aea-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90aea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90aea-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,
    [in]  PCCOR_SIGNATURE  pvNativeType,
    [in]  ULONG            cbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90aea-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="90aea-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="90aea-106">окне Токен для целевого элемента данных.</span><span class="sxs-lookup"><span data-stu-id="90aea-106">[in] The token for target data item.</span></span> <span data-ttu-id="90aea-107">Это либо маркер, либо `mdFieldDef` `mdParamDef` .</span><span class="sxs-lookup"><span data-stu-id="90aea-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="90aea-108">окне Сигнатура для неуправляемого типа.</span><span class="sxs-lookup"><span data-stu-id="90aea-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="90aea-109">окне Число байтов в `pvNativeType` .</span><span class="sxs-lookup"><span data-stu-id="90aea-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90aea-110">Требования</span><span class="sxs-lookup"><span data-stu-id="90aea-110">Requirements</span></span>  

 <span data-ttu-id="90aea-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90aea-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90aea-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="90aea-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90aea-113">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="90aea-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90aea-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90aea-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90aea-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="90aea-115">See also</span></span>

- [<span data-ttu-id="90aea-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="90aea-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="90aea-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="90aea-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
