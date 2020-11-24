---
title: Метод IMetaDataTables::GetNextBlob
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type:
- apiref
ms.openlocfilehash: ba694f485d5a51870a1283b6ccbcb7b042a14501
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685647"
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="1fabf-102">Метод IMetaDataTables::GetNextBlob</span><span class="sxs-lookup"><span data-stu-id="1fabf-102">IMetaDataTables::GetNextBlob Method</span></span>

<span data-ttu-id="1fabf-103">Возвращает индекс следующего большого двоичного объекта (BLOB) в таблице.</span><span class="sxs-lookup"><span data-stu-id="1fabf-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fabf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1fabf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fabf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1fabf-105">Parameters</span></span>  

 `ixBlob`  
 <span data-ttu-id="1fabf-106">окне Индекс, возвращенный из столбца больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="1fabf-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="1fabf-107">заполняет Указатель на индекс следующего большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="1fabf-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fabf-108">Требования</span><span class="sxs-lookup"><span data-stu-id="1fabf-108">Requirements</span></span>  

 <span data-ttu-id="1fabf-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fabf-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fabf-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="1fabf-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1fabf-111">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1fabf-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1fabf-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fabf-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fabf-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1fabf-113">See also</span></span>

- [<span data-ttu-id="1fabf-114">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="1fabf-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="1fabf-115">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="1fabf-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
