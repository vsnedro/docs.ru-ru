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
ms.openlocfilehash: b79dbdd64ac171d1bc4cd30b96ee76b4a853afb6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727254"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="61561-102">Метод IMetaDataTables::GetNextString</span><span class="sxs-lookup"><span data-stu-id="61561-102">IMetaDataTables::GetNextString Method</span></span>

<span data-ttu-id="61561-103">Возвращает индекс следующей строки в текущем столбце таблицы.</span><span class="sxs-lookup"><span data-stu-id="61561-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61561-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61561-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextString (
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61561-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="61561-105">Parameters</span></span>  

 `ixString`  
 <span data-ttu-id="61561-106">окне Значение индекса из столбца таблицы строк.</span><span class="sxs-lookup"><span data-stu-id="61561-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="61561-107">заполняет Указатель на индекс следующей строки в столбце.</span><span class="sxs-lookup"><span data-stu-id="61561-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61561-108">Требования</span><span class="sxs-lookup"><span data-stu-id="61561-108">Requirements</span></span>  

 <span data-ttu-id="61561-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61561-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61561-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="61561-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="61561-111">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="61561-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="61561-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61561-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61561-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="61561-113">See also</span></span>

- [<span data-ttu-id="61561-114">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="61561-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="61561-115">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="61561-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
