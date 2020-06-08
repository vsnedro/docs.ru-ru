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
ms.openlocfilehash: 086448248364403b718408ad8bd32e48447742d0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490386"
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="a46a7-102">Метод IMetaDataTables::GetNextBlob</span><span class="sxs-lookup"><span data-stu-id="a46a7-102">IMetaDataTables::GetNextBlob Method</span></span>
<span data-ttu-id="a46a7-103">Возвращает индекс следующего большого двоичного объекта (BLOB) в таблице.</span><span class="sxs-lookup"><span data-stu-id="a46a7-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a46a7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a46a7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a46a7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a46a7-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="a46a7-106">окне Индекс, возвращенный из столбца больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="a46a7-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="a46a7-107">заполняет Указатель на индекс следующего большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="a46a7-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a46a7-108">Требования</span><span class="sxs-lookup"><span data-stu-id="a46a7-108">Requirements</span></span>  
 <span data-ttu-id="a46a7-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a46a7-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a46a7-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="a46a7-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a46a7-111">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a46a7-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a46a7-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a46a7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a46a7-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a46a7-113">See also</span></span>

- [<span data-ttu-id="a46a7-114">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="a46a7-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="a46a7-115">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="a46a7-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
