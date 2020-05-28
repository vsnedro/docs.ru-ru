---
title: Метод IMetaDataAssemblyImport::GetManifestResourceProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
ms.openlocfilehash: c0b6d53ce3be3aed6a577bf6e38a281928499848
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009032"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="497a4-102">Метод IMetaDataAssemblyImport::GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="497a4-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="497a4-103">Возвращает набор свойств ресурса манифеста с указанной сигнатурой метаданных.</span><span class="sxs-lookup"><span data-stu-id="497a4-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="497a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="497a4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] mdToken              *ptkImplementation,
    [out] DWORD                *pdwOffset,
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="497a4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="497a4-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="497a4-106">окне `mdManifestResource`Токен, представляющий ресурс, для которого необходимо получить свойства.</span><span class="sxs-lookup"><span data-stu-id="497a4-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="497a4-107">заполняет Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="497a4-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="497a4-108">окне Размер (в расширенных символах) для `szName` .</span><span class="sxs-lookup"><span data-stu-id="497a4-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="497a4-109">заполняет Указатель на число расширенных символов, фактически возвращаемых в `szName` .</span><span class="sxs-lookup"><span data-stu-id="497a4-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="497a4-110">заполняет Указатель на `mdFile` маркер или `mdAssemblyRef` маркер, представляющий файл или сборку соответственно, который содержит ресурс.</span><span class="sxs-lookup"><span data-stu-id="497a4-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="497a4-111">заполняет Указатель на значение, указывающее смещение к началу ресурса в файле.</span><span class="sxs-lookup"><span data-stu-id="497a4-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="497a4-112">заполняет Указатель на флаги, описывающие метаданные, применяемые к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="497a4-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="497a4-113">Значение Flags является сочетанием одного или нескольких значений [корманифестресаурцефлагс](cormanifestresourceflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="497a4-113">The flags value is a combination of one or more [CorManifestResourceFlags](cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="497a4-114">Требования</span><span class="sxs-lookup"><span data-stu-id="497a4-114">Requirements</span></span>  
 <span data-ttu-id="497a4-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="497a4-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="497a4-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="497a4-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="497a4-117">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="497a4-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="497a4-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="497a4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="497a4-119">См. также статью</span><span class="sxs-lookup"><span data-stu-id="497a4-119">See also</span></span>

- [<span data-ttu-id="497a4-120">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="497a4-120">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
