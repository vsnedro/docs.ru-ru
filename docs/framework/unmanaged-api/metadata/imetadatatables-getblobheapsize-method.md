---
title: Метод IMetaDataTables::GetBlobHeapSize
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlobHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlobHeapSize
helpviewer_keywords:
- GetBlobHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetBlobHeapSize method [.NET Framework metadata]
ms.assetid: 6330a9ee-8cd5-4299-86f1-b4de2c701a0d
topic_type:
- apiref
ms.openlocfilehash: e508bcae15e72ce592529cf4b68af5d75ea49038
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721963"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="c7a5a-102">Метод IMetaDataTables::GetBlobHeapSize</span><span class="sxs-lookup"><span data-stu-id="c7a5a-102">IMetaDataTables::GetBlobHeapSize Method</span></span>

<span data-ttu-id="c7a5a-103">Возвращает размер кучи большого двоичного объекта (в байтах).</span><span class="sxs-lookup"><span data-stu-id="c7a5a-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7a5a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7a5a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="c7a5a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7a5a-105">Parameters</span></span>  

 `pcbBlobs`  
 <span data-ttu-id="c7a5a-106">заполняет Указатель на размер кучи больших двоичных объектов (в байтах).</span><span class="sxs-lookup"><span data-stu-id="c7a5a-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7a5a-107">Требования</span><span class="sxs-lookup"><span data-stu-id="c7a5a-107">Requirements</span></span>  

 <span data-ttu-id="c7a5a-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7a5a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7a5a-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="c7a5a-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c7a5a-110">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c7a5a-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c7a5a-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7a5a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7a5a-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c7a5a-112">See also</span></span>

- [<span data-ttu-id="c7a5a-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="c7a5a-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="c7a5a-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="c7a5a-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
