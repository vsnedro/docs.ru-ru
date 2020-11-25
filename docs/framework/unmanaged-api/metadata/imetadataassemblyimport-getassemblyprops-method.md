---
title: Метод IMetaDataAssemblyImport::GetAssemblyProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
ms.openlocfilehash: 1e1a86cdf55812197aae653dca256fb910a7f168
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733897"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="79280-102">Метод IMetaDataAssemblyImport::GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="79280-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>

<span data-ttu-id="79280-103">Возвращает набор свойств для сборки с указанной сигнатурой метаданных.</span><span class="sxs-lookup"><span data-stu-id="79280-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79280-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79280-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79280-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="79280-105">Parameters</span></span>  

 `mda`  
 <span data-ttu-id="79280-106">[in].</span><span class="sxs-lookup"><span data-stu-id="79280-106">[in].</span></span> <span data-ttu-id="79280-107">`mdAssembly`Токен метаданных, представляющий сборку, для которой необходимо получить свойства.</span><span class="sxs-lookup"><span data-stu-id="79280-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="79280-108">заполняет Указатель на открытый ключ или маркер метаданных.</span><span class="sxs-lookup"><span data-stu-id="79280-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="79280-109">заполняет Число байтов в возвращенном открытом ключе.</span><span class="sxs-lookup"><span data-stu-id="79280-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="79280-110">заполняет Указатель на алгоритм, используемый для хэширования файлов в сборке.</span><span class="sxs-lookup"><span data-stu-id="79280-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="79280-111">заполняет Простое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="79280-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="79280-112">окне Размер (в расширенных символах) для `szName` .</span><span class="sxs-lookup"><span data-stu-id="79280-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="79280-113">заполняет Число расширенных символов, фактически возвращаемых в `szName` .</span><span class="sxs-lookup"><span data-stu-id="79280-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="79280-114">заполняет Указатель на структуру ASSEMBLYMETADATA, содержащую метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="79280-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="79280-115">заполняет Флаги, описывающие метаданные, применяемые к сборке.</span><span class="sxs-lookup"><span data-stu-id="79280-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="79280-116">Это значение представляет собой сочетание одного или нескольких значений [корассемблифлагс](corassemblyflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="79280-116">This value is a combination of one or more [CorAssemblyFlags](corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79280-117">Требования</span><span class="sxs-lookup"><span data-stu-id="79280-117">Requirements</span></span>  

 <span data-ttu-id="79280-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79280-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79280-119">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="79280-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="79280-120">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="79280-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="79280-121">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79280-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79280-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="79280-122">See also</span></span>

- [<span data-ttu-id="79280-123">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="79280-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
