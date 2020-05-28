---
title: Метод IMetaDataAssemblyEmit::SetAssemblyProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
ms.openlocfilehash: 7c6adcbcfe64f63048078b4ccba6727a58531033
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008109"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="21411-102">Метод IMetaDataAssemblyEmit::SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="21411-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>
<span data-ttu-id="21411-103">Изменяет указанную структуру метаданных `Assembly`.</span><span class="sxs-lookup"><span data-stu-id="21411-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21411-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21411-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21411-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="21411-105">Parameters</span></span>  
 `pma`  
 <span data-ttu-id="21411-106">окне Токен метаданных, указывающий `Assembly` структуру метаданных, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="21411-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="21411-107">окне Указатель на открытый ключ издателя сборки.</span><span class="sxs-lookup"><span data-stu-id="21411-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="21411-108">окне Размер в байтах для `pbPublicKey` .</span><span class="sxs-lookup"><span data-stu-id="21411-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="21411-109">окне Идентификатор хэш-алгоритма, используемого для хэширования файлов сборки.</span><span class="sxs-lookup"><span data-stu-id="21411-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="21411-110">окне Понятное для человека текстовое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="21411-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="21411-111">окне Указатель на ASSEMBLYMETADATA, содержащий сведения о версии, платформе и локали для сборки.</span><span class="sxs-lookup"><span data-stu-id="21411-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="21411-112">окне Побитовое сочетание значений [AssemblyFlags](assemblyflags-enumeration.md) , задающих различные атрибуты сборки.</span><span class="sxs-lookup"><span data-stu-id="21411-112">[in] A bitwise combination of [AssemblyFlags](assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21411-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="21411-113">Remarks</span></span>  
 <span data-ttu-id="21411-114">Чтобы создать `Assembly` структуру метаданных, используйте метод [IMetaDataAssemblyEmit::D ефинеассембли](imetadataassemblyemit-defineassembly-method.md) .</span><span class="sxs-lookup"><span data-stu-id="21411-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21411-115">Требования</span><span class="sxs-lookup"><span data-stu-id="21411-115">Requirements</span></span>  
 <span data-ttu-id="21411-116">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21411-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21411-117">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="21411-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="21411-118">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="21411-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="21411-119">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21411-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21411-120">См. также статью</span><span class="sxs-lookup"><span data-stu-id="21411-120">See also</span></span>

- [<span data-ttu-id="21411-121">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="21411-121">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
