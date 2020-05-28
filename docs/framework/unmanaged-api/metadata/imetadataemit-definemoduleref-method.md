---
title: Метод IMetaDataEmit::DefineModuleRef
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineModuleRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineModuleRef
helpviewer_keywords:
- DefineModuleRef method [.NET Framework metadata]
- IMetaDataEmit::DefineModuleRef method [.NET Framework metadata]
ms.assetid: f2833594-d90b-4a71-9a53-34b12470c64a
topic_type:
- apiref
ms.openlocfilehash: efff491d92ac7910f43f76965ef98d1d0e4ba0aa
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004443"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="f28a1-102">Метод IMetaDataEmit::DefineModuleRef</span><span class="sxs-lookup"><span data-stu-id="f28a1-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="f28a1-103">Создает подпись метаданных для модуля с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="f28a1-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f28a1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f28a1-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (
    [in]  LPCWSTR           szName,
    [out] mdModuleRef       *pmur
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f28a1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f28a1-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="f28a1-106">окне Имя другого файла метаданных, обычно DLL.</span><span class="sxs-lookup"><span data-stu-id="f28a1-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="f28a1-107">Это только имя файла.</span><span class="sxs-lookup"><span data-stu-id="f28a1-107">This is the file name only.</span></span> <span data-ttu-id="f28a1-108">Не используйте полное имя пути.</span><span class="sxs-lookup"><span data-stu-id="f28a1-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="f28a1-109">заполняет Назначенный `mdModuleRef` маркер.</span><span class="sxs-lookup"><span data-stu-id="f28a1-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f28a1-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f28a1-110">Requirements</span></span>  
 <span data-ttu-id="f28a1-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f28a1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f28a1-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="f28a1-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f28a1-113">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f28a1-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f28a1-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f28a1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f28a1-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="f28a1-115">See also</span></span>

- [<span data-ttu-id="f28a1-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f28a1-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f28a1-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f28a1-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
