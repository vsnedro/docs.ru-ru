---
title: Метод IMetaDataAssemblyImport::GetAssemblyFromScope
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope method [.NET Framework metadata]
- GetAssemblyFromScope method [.NET Framework metadata]
ms.assetid: 0b437f70-561d-48c7-abe0-0cb9ace10c08
topic_type:
- apiref
ms.openlocfilehash: dc40b4a7cf61f8d6141b8e3e57c5e13fe2261b35
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731570"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="3845b-102">Метод IMetaDataAssemblyImport::GetAssemblyFromScope</span><span class="sxs-lookup"><span data-stu-id="3845b-102">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>

<span data-ttu-id="3845b-103">Возвращает указатель на сборку в текущей области.</span><span class="sxs-lookup"><span data-stu-id="3845b-103">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3845b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3845b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3845b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3845b-105">Parameters</span></span>  

 `ptkAssembly`  
 <span data-ttu-id="3845b-106">заполняет Указатель на полученный `mdAssembly` токен, идентифицирующий сборку.</span><span class="sxs-lookup"><span data-stu-id="3845b-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3845b-107">Требования</span><span class="sxs-lookup"><span data-stu-id="3845b-107">Requirements</span></span>  

 <span data-ttu-id="3845b-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3845b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3845b-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="3845b-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3845b-110">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3845b-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3845b-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3845b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3845b-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3845b-112">See also</span></span>

- [<span data-ttu-id="3845b-113">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="3845b-113">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
