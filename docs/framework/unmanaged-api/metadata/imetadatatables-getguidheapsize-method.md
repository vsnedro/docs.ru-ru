---
title: Метод IMetaDataTables::GetGuidHeapSize
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuidHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuidHeapSize
helpviewer_keywords:
- GetGuidHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetGuidHeapSize method [.NET Framework metadata]
ms.assetid: e875cbee-1ad9-4f1a-bf03-38cdb8ff371a
topic_type:
- apiref
ms.openlocfilehash: 1b524067ac72dfd3bd19475f11d4ec12a307731d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702437"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="89645-102">Метод IMetaDataTables::GetGuidHeapSize</span><span class="sxs-lookup"><span data-stu-id="89645-102">IMetaDataTables::GetGuidHeapSize Method</span></span>

<span data-ttu-id="89645-103">Возвращает размер кучи GUID в байтах.</span><span class="sxs-lookup"><span data-stu-id="89645-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89645-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89645-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89645-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="89645-105">Parameters</span></span>  

 `pcbGuids`  
 <span data-ttu-id="89645-106">заполняет Указатель на размер кучи GUID в байтах.</span><span class="sxs-lookup"><span data-stu-id="89645-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89645-107">Требования</span><span class="sxs-lookup"><span data-stu-id="89645-107">Requirements</span></span>  

 <span data-ttu-id="89645-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89645-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89645-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="89645-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="89645-110">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89645-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="89645-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89645-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89645-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="89645-112">See also</span></span>

- [<span data-ttu-id="89645-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="89645-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="89645-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="89645-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
