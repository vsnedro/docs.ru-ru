---
title: Метод IMetaDataEmit::Save
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Save
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type:
- apiref
ms.openlocfilehash: cef238239417a0a30cd94eaa8bd60968cfa78859
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722002"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="3130d-102">Метод IMetaDataEmit::Save</span><span class="sxs-lookup"><span data-stu-id="3130d-102">IMetaDataEmit::Save Method</span></span>

<span data-ttu-id="3130d-103">Сохраняет все метаданные в текущей области в файле по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="3130d-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3130d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3130d-104">Syntax</span></span>  
  
```cpp  
HRESULT Save (
    [in]  LPCWSTR     szFile,
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3130d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3130d-105">Parameters</span></span>  

 `wzFile`  
 <span data-ttu-id="3130d-106">окне Имя файла, в который необходимо выполнить сохранение.</span><span class="sxs-lookup"><span data-stu-id="3130d-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="3130d-107">Если это значение равно null, копия в памяти будет сохранена в последнем используемом расположении.</span><span class="sxs-lookup"><span data-stu-id="3130d-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="3130d-108">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="3130d-108">[in] Reserved.</span></span> <span data-ttu-id="3130d-109">Должен равняться нулю.</span><span class="sxs-lookup"><span data-stu-id="3130d-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3130d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3130d-110">Requirements</span></span>  

 <span data-ttu-id="3130d-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3130d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3130d-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="3130d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3130d-113">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3130d-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3130d-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3130d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3130d-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3130d-115">See also</span></span>

- [<span data-ttu-id="3130d-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="3130d-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="3130d-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="3130d-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
