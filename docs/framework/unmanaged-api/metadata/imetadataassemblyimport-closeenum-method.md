---
title: Метод IMetaDataAssemblyImport::CloseEnum
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::CloseEnum
helpviewer_keywords:
- CloseEnum method, IMetaDataAssemblyImport interface [.NET Framework metadata]
- IMetaDataAssemblyImport::CloseEnum method [.NET Framework metadata]
ms.assetid: c9df4087-12b3-46d9-b075-9067dd7805df
topic_type:
- apiref
ms.openlocfilehash: 63e81e822eb55b4090aeee6d6be3c72adbd94451
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009136"
---
# <a name="imetadataassemblyimportcloseenum-method"></a><span data-ttu-id="a3d29-102">Метод IMetaDataAssemblyImport::CloseEnum</span><span class="sxs-lookup"><span data-stu-id="a3d29-102">IMetaDataAssemblyImport::CloseEnum Method</span></span>
<span data-ttu-id="a3d29-103">Освобождает ссылку на указанный экземпляр перечисления.</span><span class="sxs-lookup"><span data-stu-id="a3d29-103">Releases a reference to the specified enumeration instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3d29-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a3d29-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
    [in] HCORENUM     hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3d29-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a3d29-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="a3d29-106">окне Экземпляр перечисления, который должен быть закрыт.</span><span class="sxs-lookup"><span data-stu-id="a3d29-106">[in] The enumeration instance to be closed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3d29-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a3d29-107">Requirements</span></span>  
 <span data-ttu-id="a3d29-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3d29-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3d29-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="a3d29-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a3d29-110">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a3d29-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a3d29-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3d29-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3d29-112">См. также статью</span><span class="sxs-lookup"><span data-stu-id="a3d29-112">See also</span></span>

- [<span data-ttu-id="a3d29-113">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="a3d29-113">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
