---
title: Метод IMetaDataTables::GetColumnInfo
ms.date: 10/10/2019
api_name:
- IMetaDataTables.GetColumnInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type:
- apiref
ms.openlocfilehash: a044924810016eea60682b8765aeee448b552f0d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501200"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="f71ac-102">Метод IMetaDataTables::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="f71ac-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="f71ac-103">Получает данные о указанном столбце в указанной таблице.</span><span class="sxs-lookup"><span data-stu-id="f71ac-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f71ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f71ac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumnInfo (
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f71ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f71ac-105">Parameters</span></span>
=======

 `ixTbl`  
 <span data-ttu-id="f71ac-106">окне Индекс требуемой таблицы.</span><span class="sxs-lookup"><span data-stu-id="f71ac-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="f71ac-107">окне Индекс нужного столбца.</span><span class="sxs-lookup"><span data-stu-id="f71ac-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="f71ac-108">заполняет Указатель на смещение столбца в строке.</span><span class="sxs-lookup"><span data-stu-id="f71ac-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="f71ac-109">заполняет Указатель на размер столбца в байтах.</span><span class="sxs-lookup"><span data-stu-id="f71ac-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="f71ac-110">заполняет Указатель на тип значений в столбце.</span><span class="sxs-lookup"><span data-stu-id="f71ac-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="f71ac-111">заполняет Указатель на указатель на имя столбца.</span><span class="sxs-lookup"><span data-stu-id="f71ac-111">[out] A pointer to a pointer to the column name.</span></span>  

## <a name="remarks"></a><span data-ttu-id="f71ac-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="f71ac-112">Remarks</span></span>

<span data-ttu-id="f71ac-113">Возвращаемый тип столбца попадает в диапазон значений:</span><span class="sxs-lookup"><span data-stu-id="f71ac-113">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="f71ac-114">птипе</span><span class="sxs-lookup"><span data-stu-id="f71ac-114">pType</span></span>                    | <span data-ttu-id="f71ac-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f71ac-115">Description</span></span>   | <span data-ttu-id="f71ac-116">Вспомогательная функция</span><span class="sxs-lookup"><span data-stu-id="f71ac-116">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="f71ac-117">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="f71ac-117">`0`..`iRidMax`</span></span><br><span data-ttu-id="f71ac-118">(0.. 63)</span><span class="sxs-lookup"><span data-stu-id="f71ac-118">(0..63)</span></span>   | <span data-ttu-id="f71ac-119">Избежать</span><span class="sxs-lookup"><span data-stu-id="f71ac-119">Rid</span></span>           | <span data-ttu-id="f71ac-120">**исридтипе**</span><span class="sxs-lookup"><span data-stu-id="f71ac-120">**IsRidType**</span></span><br><span data-ttu-id="f71ac-121">**исридортокен**</span><span class="sxs-lookup"><span data-stu-id="f71ac-121">**IsRidOrToken**</span></span> |
| <span data-ttu-id="f71ac-122">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="f71ac-122">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="f71ac-123">(64.. 95)</span><span class="sxs-lookup"><span data-stu-id="f71ac-123">(64..95)</span></span> | <span data-ttu-id="f71ac-124">Закодированный маркер</span><span class="sxs-lookup"><span data-stu-id="f71ac-124">Coded token</span></span> | <span data-ttu-id="f71ac-125">**искодедтокентипе**</span><span class="sxs-lookup"><span data-stu-id="f71ac-125">**IsCodedTokenType**</span></span> <br><span data-ttu-id="f71ac-126">**исридортокен**</span><span class="sxs-lookup"><span data-stu-id="f71ac-126">**IsRidOrToken**</span></span> |
| <span data-ttu-id="f71ac-127">`iSHORT`(96)</span><span class="sxs-lookup"><span data-stu-id="f71ac-127">`iSHORT` (96)</span></span>            | <span data-ttu-id="f71ac-128">Int16</span><span class="sxs-lookup"><span data-stu-id="f71ac-128">Int16</span></span>         | <span data-ttu-id="f71ac-129">**исфикседтипе**</span><span class="sxs-lookup"><span data-stu-id="f71ac-129">**IsFixedType**</span></span>                   |
| <span data-ttu-id="f71ac-130">`iUSHORT`(97)</span><span class="sxs-lookup"><span data-stu-id="f71ac-130">`iUSHORT` (97)</span></span>           | <span data-ttu-id="f71ac-131">UInt16</span><span class="sxs-lookup"><span data-stu-id="f71ac-131">UInt16</span></span>        | <span data-ttu-id="f71ac-132">**исфикседтипе**</span><span class="sxs-lookup"><span data-stu-id="f71ac-132">**IsFixedType**</span></span>                   |
| <span data-ttu-id="f71ac-133">`iLONG`(98)</span><span class="sxs-lookup"><span data-stu-id="f71ac-133">`iLONG` (98)</span></span>             | <span data-ttu-id="f71ac-134">Int32</span><span class="sxs-lookup"><span data-stu-id="f71ac-134">Int32</span></span>         | <span data-ttu-id="f71ac-135">**исфикседтипе**</span><span class="sxs-lookup"><span data-stu-id="f71ac-135">**IsFixedType**</span></span>                   |
| <span data-ttu-id="f71ac-136">`iULONG`(99)</span><span class="sxs-lookup"><span data-stu-id="f71ac-136">`iULONG` (99)</span></span>            | <span data-ttu-id="f71ac-137">UInt32</span><span class="sxs-lookup"><span data-stu-id="f71ac-137">UInt32</span></span>        | <span data-ttu-id="f71ac-138">**исфикседтипе**</span><span class="sxs-lookup"><span data-stu-id="f71ac-138">**IsFixedType**</span></span>                   |
| <span data-ttu-id="f71ac-139">`iBYTE`(100)</span><span class="sxs-lookup"><span data-stu-id="f71ac-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="f71ac-140">Byte</span><span class="sxs-lookup"><span data-stu-id="f71ac-140">Byte</span></span>          | <span data-ttu-id="f71ac-141">**исфикседтипе**</span><span class="sxs-lookup"><span data-stu-id="f71ac-141">**IsFixedType**</span></span>                   |
| <span data-ttu-id="f71ac-142">`iSTRING`(101)</span><span class="sxs-lookup"><span data-stu-id="f71ac-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="f71ac-143">Строка</span><span class="sxs-lookup"><span data-stu-id="f71ac-143">String</span></span>        | <span data-ttu-id="f71ac-144">**ишеаптипе**</span><span class="sxs-lookup"><span data-stu-id="f71ac-144">**IsHeapType**</span></span>                    |
| <span data-ttu-id="f71ac-145">`iGUID`(102)</span><span class="sxs-lookup"><span data-stu-id="f71ac-145">`iGUID` (102)</span></span>            | <span data-ttu-id="f71ac-146">Guid</span><span class="sxs-lookup"><span data-stu-id="f71ac-146">Guid</span></span>          | <span data-ttu-id="f71ac-147">**ишеаптипе**</span><span class="sxs-lookup"><span data-stu-id="f71ac-147">**IsHeapType**</span></span>                    |
| <span data-ttu-id="f71ac-148">`iBLOB`(103)</span><span class="sxs-lookup"><span data-stu-id="f71ac-148">`iBLOB` (103)</span></span>            | <span data-ttu-id="f71ac-149">BLOB-объект</span><span class="sxs-lookup"><span data-stu-id="f71ac-149">Blob</span></span>          | <span data-ttu-id="f71ac-150">**ишеаптипе**</span><span class="sxs-lookup"><span data-stu-id="f71ac-150">**IsHeapType**</span></span>                    |

<span data-ttu-id="f71ac-151">Значения, хранящиеся в *куче* (т `IsHeapType == true` . е.), можно считывать с помощью:</span><span class="sxs-lookup"><span data-stu-id="f71ac-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="f71ac-152">`iSTRING`: **IMetadataTables. GetString**</span><span class="sxs-lookup"><span data-stu-id="f71ac-152">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="f71ac-153">`iGUID`: **IMetadataTables. с GUID**</span><span class="sxs-lookup"><span data-stu-id="f71ac-153">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="f71ac-154">`iBLOB`: **IMetadataTables. BLOB**</span><span class="sxs-lookup"><span data-stu-id="f71ac-154">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f71ac-155">Чтобы использовать константы, определенные в приведенной выше таблице, включите директиву, `#define _DEFINE_META_DATA_META_CONSTANTS` предоставленную файлом заголовка *COR. h* .</span><span class="sxs-lookup"><span data-stu-id="f71ac-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="f71ac-156">Требования</span><span class="sxs-lookup"><span data-stu-id="f71ac-156">Requirements</span></span>  
 <span data-ttu-id="f71ac-157">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f71ac-157">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f71ac-158">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="f71ac-158">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f71ac-159">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f71ac-159">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f71ac-160">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f71ac-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f71ac-161">См. также</span><span class="sxs-lookup"><span data-stu-id="f71ac-161">See also</span></span>

- [<span data-ttu-id="f71ac-162">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="f71ac-162">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="f71ac-163">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="f71ac-163">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
