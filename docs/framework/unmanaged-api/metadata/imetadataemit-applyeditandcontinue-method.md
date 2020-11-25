---
title: Метод IMetaDataEmit::ApplyEditAndContinue
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.ApplyEditAndContinue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::ApplyEditAndContinue
helpviewer_keywords:
- ApplyEditAndContinue method [.NET Framework metadata]
- IMetaDataEmit::ApplyEditAndContinue method [.NET Framework metadata]
ms.assetid: 35991289-f389-495d-8caa-a6384fb1d557
topic_type:
- apiref
ms.openlocfilehash: 0cc84893c4937bf6b23eae0d63b92b3b871901dd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700578"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="2a858-102">Метод IMetaDataEmit::ApplyEditAndContinue</span><span class="sxs-lookup"><span data-stu-id="2a858-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>

<span data-ttu-id="2a858-103">Обновляет текущую область сборки изменениями, внесенными в указанные метаданные.</span><span class="sxs-lookup"><span data-stu-id="2a858-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a858-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a858-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyEditAndContinue (
    [in]  IUnknown    *pImport  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a858-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2a858-105">Parameters</span></span>  

 `pImport`  
 <span data-ttu-id="2a858-106">\[в \] указателе на объект [IUnknown](/cpp/atl/iunknown) , представляющий разностные метаданные из переносимого исполняемого файла (PE).</span><span class="sxs-lookup"><span data-stu-id="2a858-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="2a858-107">Разностные метаданные — это блок метаданных, включающий изменения, внесенные в копию фактических метаданных модуля.</span><span class="sxs-lookup"><span data-stu-id="2a858-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a858-108">Требования</span><span class="sxs-lookup"><span data-stu-id="2a858-108">Requirements</span></span>  

 <span data-ttu-id="2a858-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a858-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a858-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="2a858-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a858-111">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2a858-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a858-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a858-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a858-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2a858-113">See also</span></span>

- [<span data-ttu-id="2a858-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2a858-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2a858-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2a858-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
