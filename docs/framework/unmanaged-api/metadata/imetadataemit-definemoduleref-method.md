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
ms.openlocfilehash: 96d24705d80dabcda691edec497a4a30b6d37dc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719558"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="5d7b3-102">Метод IMetaDataEmit::DefineModuleRef</span><span class="sxs-lookup"><span data-stu-id="5d7b3-102">IMetaDataEmit::DefineModuleRef Method</span></span>

<span data-ttu-id="5d7b3-103">Создает подпись метаданных для модуля с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d7b3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d7b3-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (
    [in]  LPCWSTR           szName,
    [out] mdModuleRef       *pmur
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d7b3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d7b3-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="5d7b3-106">окне Имя другого файла метаданных, обычно DLL.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="5d7b3-107">Это только имя файла.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-107">This is the file name only.</span></span> <span data-ttu-id="5d7b3-108">Не используйте полное имя пути.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="5d7b3-109">заполняет Назначенный `mdModuleRef` маркер.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d7b3-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5d7b3-110">Requirements</span></span>  

 <span data-ttu-id="5d7b3-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d7b3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d7b3-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="5d7b3-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5d7b3-113">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d7b3-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d7b3-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d7b3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d7b3-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5d7b3-115">See also</span></span>

- [<span data-ttu-id="5d7b3-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="5d7b3-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="5d7b3-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="5d7b3-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
