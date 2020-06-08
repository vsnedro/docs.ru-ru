---
title: Метод IMetaDataTables::GetTableInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
ms.openlocfilehash: 7e60dd9535809ca13f3bbe6ac76f5ea1209df734
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501185"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="52bf9-102">Метод IMetaDataTables::GetTableInfo</span><span class="sxs-lookup"><span data-stu-id="52bf9-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="52bf9-103">Возвращает имя, размер строки, число строк, число столбцов и индекс ключевого столбца указанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="52bf9-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52bf9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52bf9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52bf9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="52bf9-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="52bf9-106">окне Идентификатор таблицы, свойства которой должны быть возвращены.</span><span class="sxs-lookup"><span data-stu-id="52bf9-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="52bf9-107">заполняет Указатель на размер строки таблицы в байтах.</span><span class="sxs-lookup"><span data-stu-id="52bf9-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="52bf9-108">заполняет Указатель на число строк в таблице.</span><span class="sxs-lookup"><span data-stu-id="52bf9-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="52bf9-109">заполняет Указатель на число столбцов в таблице.</span><span class="sxs-lookup"><span data-stu-id="52bf9-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="52bf9-110">заполняет Указатель на индекс ключевого столбца или значение-1, если у таблицы нет ключевого столбца.</span><span class="sxs-lookup"><span data-stu-id="52bf9-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="52bf9-111">заполняет Указатель на указатель на имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="52bf9-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52bf9-112">Требования</span><span class="sxs-lookup"><span data-stu-id="52bf9-112">Requirements</span></span>  
 <span data-ttu-id="52bf9-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52bf9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52bf9-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="52bf9-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="52bf9-115">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="52bf9-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="52bf9-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52bf9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52bf9-117">См. также</span><span class="sxs-lookup"><span data-stu-id="52bf9-117">See also</span></span>

- [<span data-ttu-id="52bf9-118">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="52bf9-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="52bf9-119">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="52bf9-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
