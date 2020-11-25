---
title: Метод IMetaDataImport::GetModuleFromScope
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type:
- apiref
ms.openlocfilehash: 2eddd7a80c2b9c1b71f3e7fc5b1e4686ba11bccd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733169"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="ef674-102">Метод IMetaDataImport::GetModuleFromScope</span><span class="sxs-lookup"><span data-stu-id="ef674-102">IMetaDataImport::GetModuleFromScope Method</span></span>

<span data-ttu-id="ef674-103">Возвращает маркер метаданных для модуля, на который ссылается текущая область метаданных.</span><span class="sxs-lookup"><span data-stu-id="ef674-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef674-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef674-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef674-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ef674-105">Parameters</span></span>  

 `pmd`  
 <span data-ttu-id="ef674-106">заполняет Указатель на маркер, представляющий модуль, на который ссылается текущая область метаданных.</span><span class="sxs-lookup"><span data-stu-id="ef674-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef674-107">Требования</span><span class="sxs-lookup"><span data-stu-id="ef674-107">Requirements</span></span>  

 <span data-ttu-id="ef674-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef674-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef674-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="ef674-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ef674-110">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ef674-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ef674-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef674-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef674-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ef674-112">See also</span></span>

- [<span data-ttu-id="ef674-113">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ef674-113">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ef674-114">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ef674-114">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
