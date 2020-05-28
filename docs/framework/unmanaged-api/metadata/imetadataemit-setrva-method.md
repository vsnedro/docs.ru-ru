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
ms.openlocfilehash: 3059d30f3969b4e19cee5a8d7a34c606f3849c05
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008746"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="81fc3-102">Метод IMetaDataEmit::SetRVA</span><span class="sxs-lookup"><span data-stu-id="81fc3-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="81fc3-103">Задает относительный виртуальный адрес указанного метода.</span><span class="sxs-lookup"><span data-stu-id="81fc3-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81fc3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81fc3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,
    [in]  ULONG        ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81fc3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="81fc3-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="81fc3-106">окне Токен для реализации целевого метода или метода.</span><span class="sxs-lookup"><span data-stu-id="81fc3-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="81fc3-107">окне Адрес кода или области данных.</span><span class="sxs-lookup"><span data-stu-id="81fc3-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81fc3-108">Требования</span><span class="sxs-lookup"><span data-stu-id="81fc3-108">Requirements</span></span>  
 <span data-ttu-id="81fc3-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81fc3-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81fc3-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="81fc3-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="81fc3-111">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="81fc3-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81fc3-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81fc3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81fc3-113">См. также статью</span><span class="sxs-lookup"><span data-stu-id="81fc3-113">See also</span></span>

- [<span data-ttu-id="81fc3-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="81fc3-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="81fc3-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="81fc3-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
