---
title: Метод IMetaDataTables::GetNextUserString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextUserString
helpviewer_keywords:
- GetNextUserString method [.NET Framework metadata]
- IMetaDataTables::GetNextUserString method [.NET Framework metadata]
ms.assetid: b7cb40ee-67b7-4f4e-8dcc-ee7ac8bc986b
topic_type:
- apiref
ms.openlocfilehash: 3490eec7c3b59ab8f4158498e2731773b6491b42
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490189"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="a2c04-102">Метод IMetaDataTables::GetNextUserString</span><span class="sxs-lookup"><span data-stu-id="a2c04-102">IMetaDataTables::GetNextUserString Method</span></span>
<span data-ttu-id="a2c04-103">Возвращает индекс строки, содержащей следующую жестко заданную строку в текущем столбце таблицы.</span><span class="sxs-lookup"><span data-stu-id="a2c04-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2c04-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2c04-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2c04-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a2c04-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="a2c04-106">окне Значение индекса из текущего строкового столбца.</span><span class="sxs-lookup"><span data-stu-id="a2c04-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="a2c04-107">заполняет Указатель на индекс строки следующей строки в столбце.</span><span class="sxs-lookup"><span data-stu-id="a2c04-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2c04-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="a2c04-108">Remarks</span></span>  
 <span data-ttu-id="a2c04-109">Мы не рекомендуем использовать этот метод, так как он не возвращает последовательные результаты.</span><span class="sxs-lookup"><span data-stu-id="a2c04-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="a2c04-110">Сведения о таблице GUID см. в документации по Common Language Infrastructure (CLI), особенно в разделе "Partition II: определение метаданных и семантика".</span><span class="sxs-lookup"><span data-stu-id="a2c04-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="a2c04-111">Документация доступна в Интернете; см. раздел [ECMA C# and Common Language Infrastructure](../../../standard/components.md#applicable-standards) Standards и [Standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="a2c04-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2c04-112">Требования</span><span class="sxs-lookup"><span data-stu-id="a2c04-112">Requirements</span></span>  
 <span data-ttu-id="a2c04-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2c04-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2c04-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="a2c04-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a2c04-115">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a2c04-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a2c04-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2c04-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2c04-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a2c04-117">See also</span></span>

- [<span data-ttu-id="a2c04-118">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="a2c04-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="a2c04-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="a2c04-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
