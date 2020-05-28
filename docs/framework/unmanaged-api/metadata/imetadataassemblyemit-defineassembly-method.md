---
title: Метод IMetaDataAssemblyEmit::DefineAssembly
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
ms.openlocfilehash: 17c91200730431c4c6e230b8c1561ce7c4863868
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008187"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="030dc-102">Метод IMetaDataAssemblyEmit::DefineAssembly</span><span class="sxs-lookup"><span data-stu-id="030dc-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="030dc-103">Создает `Assembly` структуру, содержащую метаданные для указанной сборки, и возвращает связанный маркер метаданных.</span><span class="sxs-lookup"><span data-stu-id="030dc-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="030dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="030dc-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="030dc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="030dc-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="030dc-106">окне Открытый ключ, определяющий издателя сборки, или значение NULL, если сборка не имеет строгого имени.</span><span class="sxs-lookup"><span data-stu-id="030dc-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="030dc-107">окне Размер в байтах для `pbPublicKey` .</span><span class="sxs-lookup"><span data-stu-id="030dc-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="030dc-108">окне Идентификатор алгоритма хэширования, используемого для шифрования файлов в сборке, или значение NULL для указания алгоритма SHA-1.</span><span class="sxs-lookup"><span data-stu-id="030dc-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="030dc-109">окне Понятное для человека текстовое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="030dc-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="030dc-110">Это значение не должно превышать 1024 символов.</span><span class="sxs-lookup"><span data-stu-id="030dc-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="030dc-111">окне Указатель на экземпляр ASSEMBLYMETADATA, содержащий сведения о версии, платформе и локали для сборки.</span><span class="sxs-lookup"><span data-stu-id="030dc-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="030dc-112">окне Сочетание значений [корассемблифлагс](corassemblyflags-enumeration.md) , описывающих функции сборки.</span><span class="sxs-lookup"><span data-stu-id="030dc-112">[in] A combination of [CorAssemblyFlags](corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="030dc-113">заполняет Указатель на маркер метаданных.</span><span class="sxs-lookup"><span data-stu-id="030dc-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="030dc-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="030dc-114">Remarks</span></span>  
 <span data-ttu-id="030dc-115">`Assembly`В манифесте может быть определена только одна структура метаданных.</span><span class="sxs-lookup"><span data-stu-id="030dc-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="030dc-116">Требования</span><span class="sxs-lookup"><span data-stu-id="030dc-116">Requirements</span></span>  
 <span data-ttu-id="030dc-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="030dc-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="030dc-118">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="030dc-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="030dc-119">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="030dc-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="030dc-120">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="030dc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="030dc-121">См. также статью</span><span class="sxs-lookup"><span data-stu-id="030dc-121">See also</span></span>

- [<span data-ttu-id="030dc-122">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="030dc-122">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
