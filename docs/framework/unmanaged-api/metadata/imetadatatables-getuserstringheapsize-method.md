---
title: Метод IMetaDataTables::GetUserStringHeapSize
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type:
- apiref
ms.openlocfilehash: 1aea017f17e29544e9288e1f57e6f84f9a2f6dae
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501109"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="876ea-102">Метод IMetaDataTables::GetUserStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="876ea-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="876ea-103">Возвращает размер (в байтах) кучи пользовательской строки.</span><span class="sxs-lookup"><span data-stu-id="876ea-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="876ea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="876ea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="876ea-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="876ea-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="876ea-106">заполняет Указатель на размер (в байтах) кучи пользовательской строки.</span><span class="sxs-lookup"><span data-stu-id="876ea-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="876ea-107">Требования</span><span class="sxs-lookup"><span data-stu-id="876ea-107">Requirements</span></span>  
 <span data-ttu-id="876ea-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="876ea-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="876ea-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="876ea-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="876ea-110">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="876ea-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="876ea-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="876ea-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="876ea-112">См. также</span><span class="sxs-lookup"><span data-stu-id="876ea-112">See also</span></span>

- [<span data-ttu-id="876ea-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="876ea-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="876ea-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="876ea-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
