---
title: Метод IMetaDataAssemblyImport::GetExportedTypeProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
ms.openlocfilehash: 944941c2356cae93ecc85f1714b4b29aefcb50ad
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008408"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="c60af-102">Метод IMetaDataAssemblyImport::GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="c60af-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="c60af-103">Возвращает набор свойств экспортированного типа с указанной сигнатурой метаданных.</span><span class="sxs-lookup"><span data-stu-id="c60af-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c60af-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c60af-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,
    [out] LPWSTR            szName,
    [in]  ULONG             cchName,
    [out] ULONG             *pchName,
    [out] mdToken           *ptkImplementation,
    [out] mdTypeDef         *ptkTypeDef,
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c60af-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c60af-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="c60af-106">окне `mdExportedType`Токен метаданных, представляющий экспортированный тип.</span><span class="sxs-lookup"><span data-stu-id="c60af-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="c60af-107">заполняет Имя экспортированного типа.</span><span class="sxs-lookup"><span data-stu-id="c60af-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="c60af-108">окне Размер (в расширенных символах) `szName` .</span><span class="sxs-lookup"><span data-stu-id="c60af-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="c60af-109">заполняет Число расширенных символов, фактически возвращаемых в`szName`</span><span class="sxs-lookup"><span data-stu-id="c60af-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="c60af-110">заполняет `mdFile` `mdAssemblyRef` Маркер метаданных, или `mdExportedType` , который содержит или разрешает доступ к свойствам экспортированного типа.</span><span class="sxs-lookup"><span data-stu-id="c60af-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="c60af-111">заполняет Указатель на `mdTypeDef` маркер, представляющий тип в файле.</span><span class="sxs-lookup"><span data-stu-id="c60af-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="c60af-112">заполняет Указатель на флаги, описывающие метаданные, применяемые к экспортируемому типу.</span><span class="sxs-lookup"><span data-stu-id="c60af-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="c60af-113">Значение Flags может быть одним или несколькими [кортипеаттр](cortypeattr-enumeration.md) значениями.</span><span class="sxs-lookup"><span data-stu-id="c60af-113">The flags value can be one or more [CorTypeAttr](cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c60af-114">Требования</span><span class="sxs-lookup"><span data-stu-id="c60af-114">Requirements</span></span>  
 <span data-ttu-id="c60af-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c60af-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c60af-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="c60af-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c60af-117">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c60af-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c60af-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c60af-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c60af-119">См. также статью</span><span class="sxs-lookup"><span data-stu-id="c60af-119">See also</span></span>

- [<span data-ttu-id="c60af-120">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="c60af-120">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
