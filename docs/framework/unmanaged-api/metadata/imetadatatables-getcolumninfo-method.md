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
ms.openlocfilehash: 227d9ab67ab3091508232be3018ca520a6b5dcc6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711056"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="15239-102">Метод IMetaDataTables::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="15239-102">IMetaDataTables::GetColumnInfo Method</span></span>

<span data-ttu-id="15239-103">Получает данные о указанном столбце в указанной таблице.</span><span class="sxs-lookup"><span data-stu-id="15239-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15239-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15239-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="15239-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="15239-105">Parameters</span></span>

=======

 `ixTbl`  
 <span data-ttu-id="15239-106">окне Индекс требуемой таблицы.</span><span class="sxs-lookup"><span data-stu-id="15239-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="15239-107">окне Индекс нужного столбца.</span><span class="sxs-lookup"><span data-stu-id="15239-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="15239-108">заполняет Указатель на смещение столбца в строке.</span><span class="sxs-lookup"><span data-stu-id="15239-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="15239-109">заполняет Указатель на размер столбца в байтах.</span><span class="sxs-lookup"><span data-stu-id="15239-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="15239-110">заполняет Указатель на тип значений в столбце.</span><span class="sxs-lookup"><span data-stu-id="15239-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="15239-111">заполняет Указатель на указатель на имя столбца.</span><span class="sxs-lookup"><span data-stu-id="15239-111">[out] A pointer to a pointer to the column name.</span></span>  

## <a name="remarks"></a><span data-ttu-id="15239-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="15239-112">Remarks</span></span>

<span data-ttu-id="15239-113">Возвращаемый тип столбца попадает в диапазон значений:</span><span class="sxs-lookup"><span data-stu-id="15239-113">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="15239-114">птипе</span><span class="sxs-lookup"><span data-stu-id="15239-114">pType</span></span>                    | <span data-ttu-id="15239-115">Описание</span><span class="sxs-lookup"><span data-stu-id="15239-115">Description</span></span>   | <span data-ttu-id="15239-116">Вспомогательная функция</span><span class="sxs-lookup"><span data-stu-id="15239-116">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="15239-117">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="15239-117">`0`..`iRidMax`</span></span><br><span data-ttu-id="15239-118">(0.. 63)</span><span class="sxs-lookup"><span data-stu-id="15239-118">(0..63)</span></span>   | <span data-ttu-id="15239-119">Избежать</span><span class="sxs-lookup"><span data-stu-id="15239-119">Rid</span></span>           | <span data-ttu-id="15239-120">**исридтипе**</span><span class="sxs-lookup"><span data-stu-id="15239-120">**IsRidType**</span></span><br><span data-ttu-id="15239-121">**исридортокен**</span><span class="sxs-lookup"><span data-stu-id="15239-121">**IsRidOrToken**</span></span> |
| <span data-ttu-id="15239-122">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="15239-122">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="15239-123">(64.. 95)</span><span class="sxs-lookup"><span data-stu-id="15239-123">(64..95)</span></span> | <span data-ttu-id="15239-124">Закодированный маркер</span><span class="sxs-lookup"><span data-stu-id="15239-124">Coded token</span></span> | <span data-ttu-id="15239-125">**искодедтокентипе**</span><span class="sxs-lookup"><span data-stu-id="15239-125">**IsCodedTokenType**</span></span> <br><span data-ttu-id="15239-126">**исридортокен**</span><span class="sxs-lookup"><span data-stu-id="15239-126">**IsRidOrToken**</span></span> |
| <span data-ttu-id="15239-127">`iSHORT` (96)</span><span class="sxs-lookup"><span data-stu-id="15239-127">`iSHORT` (96)</span></span>            | <span data-ttu-id="15239-128">Int16</span><span class="sxs-lookup"><span data-stu-id="15239-128">Int16</span></span>         | <span data-ttu-id="15239-129">**исфикседтипе**</span><span class="sxs-lookup"><span data-stu-id="15239-129">**IsFixedType**</span></span>                   |
| <span data-ttu-id="15239-130">`iUSHORT` (97)</span><span class="sxs-lookup"><span data-stu-id="15239-130">`iUSHORT` (97)</span></span>           | <span data-ttu-id="15239-131">UInt16</span><span class="sxs-lookup"><span data-stu-id="15239-131">UInt16</span></span>        | <span data-ttu-id="15239-132">**исфикседтипе**</span><span class="sxs-lookup"><span data-stu-id="15239-132">**IsFixedType**</span></span>                   |
| <span data-ttu-id="15239-133">`iLONG` (98)</span><span class="sxs-lookup"><span data-stu-id="15239-133">`iLONG` (98)</span></span>             | <span data-ttu-id="15239-134">Int32</span><span class="sxs-lookup"><span data-stu-id="15239-134">Int32</span></span>         | <span data-ttu-id="15239-135">**исфикседтипе**</span><span class="sxs-lookup"><span data-stu-id="15239-135">**IsFixedType**</span></span>                   |
| <span data-ttu-id="15239-136">`iULONG` (99)</span><span class="sxs-lookup"><span data-stu-id="15239-136">`iULONG` (99)</span></span>            | <span data-ttu-id="15239-137">UInt32</span><span class="sxs-lookup"><span data-stu-id="15239-137">UInt32</span></span>        | <span data-ttu-id="15239-138">**исфикседтипе**</span><span class="sxs-lookup"><span data-stu-id="15239-138">**IsFixedType**</span></span>                   |
| <span data-ttu-id="15239-139">`iBYTE` (100)</span><span class="sxs-lookup"><span data-stu-id="15239-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="15239-140">Byte</span><span class="sxs-lookup"><span data-stu-id="15239-140">Byte</span></span>          | <span data-ttu-id="15239-141">**исфикседтипе**</span><span class="sxs-lookup"><span data-stu-id="15239-141">**IsFixedType**</span></span>                   |
| <span data-ttu-id="15239-142">`iSTRING` (101)</span><span class="sxs-lookup"><span data-stu-id="15239-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="15239-143">Строка</span><span class="sxs-lookup"><span data-stu-id="15239-143">String</span></span>        | <span data-ttu-id="15239-144">**ишеаптипе**</span><span class="sxs-lookup"><span data-stu-id="15239-144">**IsHeapType**</span></span>                    |
| <span data-ttu-id="15239-145">`iGUID` (102)</span><span class="sxs-lookup"><span data-stu-id="15239-145">`iGUID` (102)</span></span>            | <span data-ttu-id="15239-146">Guid</span><span class="sxs-lookup"><span data-stu-id="15239-146">Guid</span></span>          | <span data-ttu-id="15239-147">**ишеаптипе**</span><span class="sxs-lookup"><span data-stu-id="15239-147">**IsHeapType**</span></span>                    |
| <span data-ttu-id="15239-148">`iBLOB` (103)</span><span class="sxs-lookup"><span data-stu-id="15239-148">`iBLOB` (103)</span></span>            | <span data-ttu-id="15239-149">BLOB-объект</span><span class="sxs-lookup"><span data-stu-id="15239-149">Blob</span></span>          | <span data-ttu-id="15239-150">**ишеаптипе**</span><span class="sxs-lookup"><span data-stu-id="15239-150">**IsHeapType**</span></span>                    |

<span data-ttu-id="15239-151">Значения, хранящиеся в *куче* (т `IsHeapType == true` . е.), можно считывать с помощью:</span><span class="sxs-lookup"><span data-stu-id="15239-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="15239-152">`iSTRING`: **IMetadataTables. GetString**</span><span class="sxs-lookup"><span data-stu-id="15239-152">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="15239-153">`iGUID`: **IMetadataTables. с GUID**</span><span class="sxs-lookup"><span data-stu-id="15239-153">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="15239-154">`iBLOB`: **IMetadataTables. BLOB**</span><span class="sxs-lookup"><span data-stu-id="15239-154">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="15239-155">Чтобы использовать константы, определенные в приведенной выше таблице, включите директиву, `#define _DEFINE_META_DATA_META_CONSTANTS` предоставленную файлом заголовка *COR. h* .</span><span class="sxs-lookup"><span data-stu-id="15239-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="15239-156">Требования</span><span class="sxs-lookup"><span data-stu-id="15239-156">Requirements</span></span>  

 <span data-ttu-id="15239-157">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15239-157">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15239-158">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="15239-158">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="15239-159">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="15239-159">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="15239-160">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15239-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15239-161">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="15239-161">See also</span></span>

- [<span data-ttu-id="15239-162">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="15239-162">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="15239-163">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="15239-163">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
