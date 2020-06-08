---
title: Метод IMetaDataTables::GetNextString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type:
- apiref
ms.openlocfilehash: 6f4764f016360a2ec0ab054b7a89ccb3f86aeb43
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490228"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="9e0ed-102">Метод IMetaDataTables::GetNextString</span><span class="sxs-lookup"><span data-stu-id="9e0ed-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="9e0ed-103">Возвращает индекс следующей строки в текущем столбце таблицы.</span><span class="sxs-lookup"><span data-stu-id="9e0ed-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e0ed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e0ed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextString (
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e0ed-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9e0ed-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="9e0ed-106">окне Значение индекса из столбца таблицы строк.</span><span class="sxs-lookup"><span data-stu-id="9e0ed-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="9e0ed-107">заполняет Указатель на индекс следующей строки в столбце.</span><span class="sxs-lookup"><span data-stu-id="9e0ed-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e0ed-108">Требования</span><span class="sxs-lookup"><span data-stu-id="9e0ed-108">Requirements</span></span>  
 <span data-ttu-id="9e0ed-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e0ed-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e0ed-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="9e0ed-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9e0ed-111">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9e0ed-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9e0ed-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e0ed-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e0ed-113">См. также</span><span class="sxs-lookup"><span data-stu-id="9e0ed-113">See also</span></span>

- [<span data-ttu-id="9e0ed-114">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="9e0ed-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="9e0ed-115">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="9e0ed-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
