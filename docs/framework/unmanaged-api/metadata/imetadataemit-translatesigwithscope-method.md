---
title: Метод IMetaDataEmit::TranslateSigWithScope
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.TranslateSigWithScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type:
- apiref
ms.openlocfilehash: 80d33da2eb2a7f0cfbe5dcb7279fff9973dada2e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712928"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="148ee-102">Метод IMetaDataEmit::TranslateSigWithScope</span><span class="sxs-lookup"><span data-stu-id="148ee-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>

<span data-ttu-id="148ee-103">Импортирует сборку в текущую область и получает новую сигнатуру метаданных для Объединенной области.</span><span class="sxs-lookup"><span data-stu-id="148ee-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="148ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="148ee-104">Syntax</span></span>  
  
```cpp  
HRESULT TranslateSigWithScope (
    [in]  IMetaDataAssemblyImport   *pAssemImport,
    [in]  const void                *pbHashValue,
    [in]  ULONG                     cbHashValue,
    [in]  IMetaDataImport           *import,
    [in]  PCCOR_SIGNATURE           pbSigBlob,
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,
    [in]  IMetaDataEmit             *emit,
    [out] PCOR_SIGNATURE            pvTranslatedSig,
    [in]  ULONG                     cbTranslatedSigMax,
    [out] ULONG                     *pcbTranslatedSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="148ee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="148ee-105">Parameters</span></span>  

 `pAssemImport`  
 <span data-ttu-id="148ee-106">окне Интерфейс для импортируемой сборки (где определена сигнатура).</span><span class="sxs-lookup"><span data-stu-id="148ee-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="148ee-107">окне Хэш-объект хэша для сборки.</span><span class="sxs-lookup"><span data-stu-id="148ee-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="148ee-108">окне Число байтов в `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="148ee-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="148ee-109">окне Интерфейс для области действия метаданных импорта.</span><span class="sxs-lookup"><span data-stu-id="148ee-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="148ee-110">окне Импортируемая подпись.</span><span class="sxs-lookup"><span data-stu-id="148ee-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="148ee-111">окне Размер (в байтах) `pbSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="148ee-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="148ee-112">окне Интерфейс для экспорта сборки.</span><span class="sxs-lookup"><span data-stu-id="148ee-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="148ee-113">окне Интерфейс для области экспорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="148ee-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="148ee-114">заполняет Буфер для хранения переведенного большого двоичного объекта сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="148ee-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="148ee-115">окне Емкость (в байтах) `pvTranslatedSig` .</span><span class="sxs-lookup"><span data-stu-id="148ee-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="148ee-116">заполняет Число фактических байтов в переведенной сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="148ee-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="148ee-117">Требования</span><span class="sxs-lookup"><span data-stu-id="148ee-117">Requirements</span></span>  

 <span data-ttu-id="148ee-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="148ee-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="148ee-119">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="148ee-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="148ee-120">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="148ee-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="148ee-121">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="148ee-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="148ee-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="148ee-122">See also</span></span>

- [<span data-ttu-id="148ee-123">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="148ee-123">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="148ee-124">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="148ee-124">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="148ee-125">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="148ee-125">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="148ee-126">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="148ee-126">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="148ee-127">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="148ee-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
