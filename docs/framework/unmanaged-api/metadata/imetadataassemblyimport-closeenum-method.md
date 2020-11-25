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
ms.openlocfilehash: d2ce26daa5f5c36e4073eee653cc650c1a8d54c9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708949"
---
# <a name="imetadataassemblyimportcloseenum-method"></a><span data-ttu-id="1261a-102">Метод IMetaDataAssemblyImport::CloseEnum</span><span class="sxs-lookup"><span data-stu-id="1261a-102">IMetaDataAssemblyImport::CloseEnum Method</span></span>

<span data-ttu-id="1261a-103">Освобождает ссылку на указанный экземпляр перечисления.</span><span class="sxs-lookup"><span data-stu-id="1261a-103">Releases a reference to the specified enumeration instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1261a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1261a-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
    [in] HCORENUM     hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1261a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1261a-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="1261a-106">окне Экземпляр перечисления, который должен быть закрыт.</span><span class="sxs-lookup"><span data-stu-id="1261a-106">[in] The enumeration instance to be closed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1261a-107">Требования</span><span class="sxs-lookup"><span data-stu-id="1261a-107">Requirements</span></span>  

 <span data-ttu-id="1261a-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1261a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1261a-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="1261a-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1261a-110">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1261a-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1261a-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1261a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1261a-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1261a-112">See also</span></span>

- [<span data-ttu-id="1261a-113">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="1261a-113">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
