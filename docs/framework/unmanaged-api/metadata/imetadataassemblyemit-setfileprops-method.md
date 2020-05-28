---
title: Метод IMetaDataAssemblyEmit::SetFileProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
ms.openlocfilehash: 9990daea1b097532de53684921d3f10c520a3b1a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008070"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="5bf79-102">Метод IMetaDataAssemblyEmit::SetFileProps</span><span class="sxs-lookup"><span data-stu-id="5bf79-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="5bf79-103">Изменяет указанную структуру метаданных `File`.</span><span class="sxs-lookup"><span data-stu-id="5bf79-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bf79-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5bf79-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bf79-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5bf79-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="5bf79-106">окне Токен метаданных, указывающий `File` структуру метаданных, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="5bf79-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="5bf79-107">окне Указатель на хэш-данные, связанные с файлом.</span><span class="sxs-lookup"><span data-stu-id="5bf79-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="5bf79-108">окне Размер в байтах для `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="5bf79-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="5bf79-109">окне Побитовое сочетание значений [корфилефлагс](corfileflags-enumeration.md) , задающих различные атрибуты файла.</span><span class="sxs-lookup"><span data-stu-id="5bf79-109">[in] A bitwise combination of [CorFileFlags](corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bf79-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="5bf79-110">Remarks</span></span>  
 <span data-ttu-id="5bf79-111">Чтобы создать `File` структуру метаданных, используйте метод [IMetaDataAssemblyEmit::D ефинефиле](imetadataassemblyemit-definefile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5bf79-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bf79-112">Требования</span><span class="sxs-lookup"><span data-stu-id="5bf79-112">Requirements</span></span>  
 <span data-ttu-id="5bf79-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bf79-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bf79-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="5bf79-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5bf79-115">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5bf79-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5bf79-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bf79-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bf79-117">См. также статью</span><span class="sxs-lookup"><span data-stu-id="5bf79-117">See also</span></span>

- [<span data-ttu-id="5bf79-118">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="5bf79-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
