---
title: Метод IMetaDataEmit::SetMethodProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
ms.openlocfilehash: c461582cc22f7185ee2707db91be83bc1aa0ba4c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706844"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="69a2a-102">Метод IMetaDataEmit::SetMethodProps</span><span class="sxs-lookup"><span data-stu-id="69a2a-102">IMetaDataEmit::SetMethodProps Method</span></span>

<span data-ttu-id="69a2a-103">Задает или обновляет компонент, хранящийся по указанному относительному виртуальному адресу метода, определенного в предыдущем вызове [IMetaDataEmit::D ефинемесод](imetadataemit-definemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="69a2a-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69a2a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69a2a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodProps (
    [in]  mdMethodDef md,
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,
    [in]  DWORD       dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69a2a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="69a2a-105">Parameters</span></span>  

 `md`  
 <span data-ttu-id="69a2a-106">окне Токен для изменяемого метода.</span><span class="sxs-lookup"><span data-stu-id="69a2a-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="69a2a-107">окне Атрибуты элемента.</span><span class="sxs-lookup"><span data-stu-id="69a2a-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="69a2a-108">окне Адрес кода.</span><span class="sxs-lookup"><span data-stu-id="69a2a-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="69a2a-109">окне Флаги реализации для метода.</span><span class="sxs-lookup"><span data-stu-id="69a2a-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69a2a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="69a2a-110">Requirements</span></span>  

 <span data-ttu-id="69a2a-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69a2a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69a2a-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="69a2a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="69a2a-113">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="69a2a-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69a2a-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69a2a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69a2a-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="69a2a-115">See also</span></span>

- [<span data-ttu-id="69a2a-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="69a2a-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="69a2a-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="69a2a-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
