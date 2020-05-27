---
title: Метод IMetaDataEmit::SetFieldProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
ms.openlocfilehash: 220556ec130c7bff7c413405820c4fee0582b051
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008018"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="c4ba7-102">Метод IMetaDataEmit::SetFieldProps</span><span class="sxs-lookup"><span data-stu-id="c4ba7-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="c4ba7-103">Задает или обновляет значение по умолчанию для поля, на которое ссылается заданный токен поля.</span><span class="sxs-lookup"><span data-stu-id="c4ba7-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4ba7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4ba7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4ba7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4ba7-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="c4ba7-106">окне Токен для целевого поля.</span><span class="sxs-lookup"><span data-stu-id="c4ba7-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="c4ba7-107">окне Атрибуты поля.</span><span class="sxs-lookup"><span data-stu-id="c4ba7-107">[in] Field attributes.</span></span> <span data-ttu-id="c4ba7-108">Это битовая маска `CorFieldAttr` значений.</span><span class="sxs-lookup"><span data-stu-id="c4ba7-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="c4ba7-109">окне `ELEMENT_TYPE_` *\** Значение для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="c4ba7-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="c4ba7-110">Это `CorElementType` значение.</span><span class="sxs-lookup"><span data-stu-id="c4ba7-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="c4ba7-111">Если константа не определена, присвойте этому параметру значение `ELEMENT_TYPE_END` .</span><span class="sxs-lookup"><span data-stu-id="c4ba7-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="c4ba7-112">окне Постоянное значение для поля.</span><span class="sxs-lookup"><span data-stu-id="c4ba7-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="c4ba7-113">окне Размер (в символах Юникода) `pValue` .</span><span class="sxs-lookup"><span data-stu-id="c4ba7-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4ba7-114">Требования</span><span class="sxs-lookup"><span data-stu-id="c4ba7-114">Requirements</span></span>  
 <span data-ttu-id="c4ba7-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4ba7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4ba7-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="c4ba7-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c4ba7-117">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c4ba7-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4ba7-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4ba7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4ba7-119">См. также статью</span><span class="sxs-lookup"><span data-stu-id="c4ba7-119">See also</span></span>

- [<span data-ttu-id="c4ba7-120">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="c4ba7-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="c4ba7-121">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c4ba7-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
