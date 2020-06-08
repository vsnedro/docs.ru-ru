---
title: Метод ICorDebugModule::GetToken
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type:
- apiref
ms.openlocfilehash: 1cf4d82200709971201da60d06d0cb929641a104
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501889"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="8cd52-102">Метод ICorDebugModule::GetToken</span><span class="sxs-lookup"><span data-stu-id="8cd52-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="8cd52-103">Возвращает маркер для записи таблицы для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="8cd52-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cd52-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8cd52-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cd52-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8cd52-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="8cd52-106">заполняет Указатель на `mdModule` маркер, который ссылается на метаданные модуля.</span><span class="sxs-lookup"><span data-stu-id="8cd52-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8cd52-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8cd52-107">Remarks</span></span>  
 <span data-ttu-id="8cd52-108">Маркер может быть передан интерфейсам импорта метаданных [IMetaDataImport](../metadata/imetadataimport-interface.md), [IMetaDataImport2](../metadata/imetadataimport2-interface.md)и [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="8cd52-108">The token can be passed to the [IMetaDataImport](../metadata/imetadataimport-interface.md), [IMetaDataImport2](../metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cd52-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8cd52-109">Requirements</span></span>  
 <span data-ttu-id="8cd52-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cd52-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cd52-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8cd52-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8cd52-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cd52-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cd52-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cd52-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cd52-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8cd52-114">See also</span></span>

- [<span data-ttu-id="8cd52-115">Метаданные</span><span class="sxs-lookup"><span data-stu-id="8cd52-115">Metadata</span></span>](../metadata/index.md)
