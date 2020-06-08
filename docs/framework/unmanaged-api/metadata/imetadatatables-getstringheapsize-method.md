---
title: Метод IMetaDataTables::GetStringHeapSize
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetStringHeapSize method [.NET Framework metadata]
- GetStringHeapSize method [.NET Framework metadata]
ms.assetid: ed8f6335-81f5-4c09-81a9-2a909fc530c9
topic_type:
- apiref
ms.openlocfilehash: 1aa7853602c1aaf484ef89d9c4fb06464e135f80
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501179"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="c7c18-102">Метод IMetaDataTables::GetStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="c7c18-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="c7c18-103">Возвращает размер кучи строк (в байтах).</span><span class="sxs-lookup"><span data-stu-id="c7c18-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7c18-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7c18-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7c18-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7c18-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="c7c18-106">заполняет Указатель на размер (в байтах) кучи строк.</span><span class="sxs-lookup"><span data-stu-id="c7c18-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7c18-107">Требования</span><span class="sxs-lookup"><span data-stu-id="c7c18-107">Requirements</span></span>  
 <span data-ttu-id="c7c18-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7c18-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7c18-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="c7c18-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c7c18-110">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c7c18-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c7c18-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7c18-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7c18-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c7c18-112">See also</span></span>

- [<span data-ttu-id="c7c18-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="c7c18-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="c7c18-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="c7c18-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
