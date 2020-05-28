---
title: Метод IMetaDataAssemblyEmit::SetAssemblyRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type:
- apiref
ms.openlocfilehash: fb381a872cbeb787da0c6920f2cdeef434fb33ea
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008096"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="22e81-102">Метод IMetaDataAssemblyEmit::SetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="22e81-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="22e81-103">Изменяет указанную структуру метаданных `AssemblyRef`.</span><span class="sxs-lookup"><span data-stu-id="22e81-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22e81-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22e81-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,
    [in] const ASSEMBLYMETADATA     *pMetaData,
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22e81-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="22e81-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="22e81-106">окне Токен метаданных, указывающий `AssemblyRef` структуру метаданных, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="22e81-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="22e81-107">окне Открытый ключ издателя сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="22e81-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="22e81-108">окне Размер в байтах для `pbPublicKeyOrToken` .</span><span class="sxs-lookup"><span data-stu-id="22e81-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="22e81-109">окне Понятное для человека текстовое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="22e81-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="22e81-110">окне Указатель на экземпляр ASSEMBLYMETADATA, содержащий сведения о версии, платформе и локали для сборки.</span><span class="sxs-lookup"><span data-stu-id="22e81-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="22e81-111">окне Указатель на хэш-данные, связанные со сборкой.</span><span class="sxs-lookup"><span data-stu-id="22e81-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="22e81-112">окне Размер в байтах для `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="22e81-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="22e81-113">окне Побитовое сочетание значений [ассемблиреффлагс](assemblyrefflags-enumeration.md) , задающих атрибуты упоминаемой сборки.</span><span class="sxs-lookup"><span data-stu-id="22e81-113">[in] A bitwise combination of [AssemblyRefFlags](assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22e81-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="22e81-114">Remarks</span></span>  
 <span data-ttu-id="22e81-115">Чтобы создать `AssemblyRef` структуру метаданных, используйте метод [IMetaDataAssemblyEmit::D ефинеассемблиреф](imetadataassemblyemit-defineassemblyref-method.md) .</span><span class="sxs-lookup"><span data-stu-id="22e81-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22e81-116">Требования</span><span class="sxs-lookup"><span data-stu-id="22e81-116">Requirements</span></span>  
 <span data-ttu-id="22e81-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22e81-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22e81-118">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="22e81-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="22e81-119">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="22e81-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="22e81-120">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22e81-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e81-121">См. также статью</span><span class="sxs-lookup"><span data-stu-id="22e81-121">See also</span></span>

- [<span data-ttu-id="22e81-122">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="22e81-122">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
