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
ms.openlocfilehash: 32224431051b958a3f01ffeb15cdb6db1dae2657
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722106"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="28e1a-102">Метод IMetaDataAssemblyImport::GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="28e1a-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>

<span data-ttu-id="28e1a-103">Возвращает набор свойств экспортированного типа с указанной сигнатурой метаданных.</span><span class="sxs-lookup"><span data-stu-id="28e1a-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28e1a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28e1a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="28e1a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="28e1a-105">Parameters</span></span>  

 `mdct`  
 <span data-ttu-id="28e1a-106">окне `mdExportedType` Токен метаданных, представляющий экспортированный тип.</span><span class="sxs-lookup"><span data-stu-id="28e1a-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="28e1a-107">заполняет Имя экспортированного типа.</span><span class="sxs-lookup"><span data-stu-id="28e1a-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="28e1a-108">окне Размер (в расширенных символах) `szName` .</span><span class="sxs-lookup"><span data-stu-id="28e1a-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="28e1a-109">заполняет Число расширенных символов, фактически возвращаемых в `szName`</span><span class="sxs-lookup"><span data-stu-id="28e1a-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="28e1a-110">заполняет `mdFile` `mdAssemblyRef` Маркер метаданных, или `mdExportedType` , который содержит или разрешает доступ к свойствам экспортированного типа.</span><span class="sxs-lookup"><span data-stu-id="28e1a-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="28e1a-111">заполняет Указатель на `mdTypeDef` маркер, представляющий тип в файле.</span><span class="sxs-lookup"><span data-stu-id="28e1a-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="28e1a-112">заполняет Указатель на флаги, описывающие метаданные, применяемые к экспортируемому типу.</span><span class="sxs-lookup"><span data-stu-id="28e1a-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="28e1a-113">Значение Flags может быть одним или несколькими [кортипеаттр](cortypeattr-enumeration.md) значениями.</span><span class="sxs-lookup"><span data-stu-id="28e1a-113">The flags value can be one or more [CorTypeAttr](cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28e1a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="28e1a-114">Requirements</span></span>  

 <span data-ttu-id="28e1a-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28e1a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28e1a-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="28e1a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="28e1a-117">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="28e1a-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="28e1a-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28e1a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28e1a-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="28e1a-119">See also</span></span>

- [<span data-ttu-id="28e1a-120">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="28e1a-120">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
