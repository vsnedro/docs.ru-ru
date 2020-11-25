---
title: Метод IMetaDataEmit::SetRVA
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
ms.openlocfilehash: df9dc1a36a9adcef3f93a9929565cef117e84d75
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704231"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="9b3ed-102">Метод IMetaDataEmit::SetRVA</span><span class="sxs-lookup"><span data-stu-id="9b3ed-102">IMetaDataEmit::SetRVA Method</span></span>

<span data-ttu-id="9b3ed-103">Задает относительный виртуальный адрес указанного метода.</span><span class="sxs-lookup"><span data-stu-id="9b3ed-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b3ed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b3ed-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,
    [in]  ULONG        ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b3ed-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9b3ed-105">Parameters</span></span>  

 `md`  
 <span data-ttu-id="9b3ed-106">окне Токен для реализации целевого метода или метода.</span><span class="sxs-lookup"><span data-stu-id="9b3ed-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="9b3ed-107">окне Адрес кода или области данных.</span><span class="sxs-lookup"><span data-stu-id="9b3ed-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b3ed-108">Требования</span><span class="sxs-lookup"><span data-stu-id="9b3ed-108">Requirements</span></span>  

 <span data-ttu-id="9b3ed-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b3ed-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b3ed-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="9b3ed-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b3ed-111">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9b3ed-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b3ed-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b3ed-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b3ed-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9b3ed-113">See also</span></span>

- [<span data-ttu-id="9b3ed-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="9b3ed-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="9b3ed-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="9b3ed-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
