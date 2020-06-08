---
title: Метод IMetaDataTables::GetNextGuid
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextGuid
helpviewer_keywords:
- GetNextGuid method [.NET Framework metadata]
- IMetaDataTables::GetNextGuid method [.NET Framework metadata]
ms.assetid: 68f6ea4d-9112-4d6b-93d9-e34f1e2f2496
topic_type:
- apiref
ms.openlocfilehash: 645a9913d0de6f93e59df3dd8ba7267ddb13b41b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490267"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="c0b31-102">Метод IMetaDataTables::GetNextGuid</span><span class="sxs-lookup"><span data-stu-id="c0b31-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="c0b31-103">Возвращает индекс следующего значения GUID в текущем столбце таблицы.</span><span class="sxs-lookup"><span data-stu-id="c0b31-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0b31-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0b31-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0b31-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0b31-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="c0b31-106">окне Значение индекса из столбца таблицы GUID.</span><span class="sxs-lookup"><span data-stu-id="c0b31-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="c0b31-107">заполняет Указатель на индекс следующего значения GUID.</span><span class="sxs-lookup"><span data-stu-id="c0b31-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0b31-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c0b31-108">Remarks</span></span>  

  <span data-ttu-id="c0b31-109">Мы не рекомендуем использовать этот метод, так как он не возвращает последовательные результаты.</span><span class="sxs-lookup"><span data-stu-id="c0b31-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="c0b31-110">Сведения о таблице GUID см. в документации по Common Language Infrastructure (CLI), особенно в разделе "Partition II: определение метаданных и семантика".</span><span class="sxs-lookup"><span data-stu-id="c0b31-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="c0b31-111">Документация доступна в Интернете; см. раздел [ECMA C# and Common Language Infrastructure](../../../standard/components.md#applicable-standards) Standards и [Standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="c0b31-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0b31-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c0b31-112">Requirements</span></span>  
 <span data-ttu-id="c0b31-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0b31-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0b31-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="c0b31-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0b31-115">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c0b31-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c0b31-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0b31-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0b31-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c0b31-117">See also</span></span>

- [<span data-ttu-id="c0b31-118">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="c0b31-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="c0b31-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="c0b31-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
