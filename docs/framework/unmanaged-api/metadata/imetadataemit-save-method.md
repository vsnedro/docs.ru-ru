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
ms.openlocfilehash: 23f6a301c4c11be92e05dbac0d4f69817d857a28
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003967"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="f0b13-102">Метод IMetaDataEmit::Save</span><span class="sxs-lookup"><span data-stu-id="f0b13-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="f0b13-103">Сохраняет все метаданные в текущей области в файле по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="f0b13-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0b13-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0b13-104">Syntax</span></span>  
  
```cpp  
HRESULT Save (
    [in]  LPCWSTR     szFile,
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0b13-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0b13-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="f0b13-106">окне Имя файла, в который необходимо выполнить сохранение.</span><span class="sxs-lookup"><span data-stu-id="f0b13-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="f0b13-107">Если это значение равно null, копия в памяти будет сохранена в последнем используемом расположении.</span><span class="sxs-lookup"><span data-stu-id="f0b13-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="f0b13-108">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="f0b13-108">[in] Reserved.</span></span> <span data-ttu-id="f0b13-109">Должен равняться нулю.</span><span class="sxs-lookup"><span data-stu-id="f0b13-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0b13-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f0b13-110">Requirements</span></span>  
 <span data-ttu-id="f0b13-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0b13-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0b13-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="f0b13-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f0b13-113">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f0b13-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0b13-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0b13-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0b13-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="f0b13-115">See also</span></span>

- [<span data-ttu-id="f0b13-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f0b13-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f0b13-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f0b13-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
