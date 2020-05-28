---
title: Метод IMetaDataEmit::DefinePinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
ms.openlocfilehash: 447ec44ed3efc4eec84d1e4acd6f2ec1a730bf74
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008031"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="fa6df-102">Метод IMetaDataEmit::DefinePinvokeMap</span><span class="sxs-lookup"><span data-stu-id="fa6df-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="fa6df-103">Задает функции сигнатуры PInvoke метода, на который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="fa6df-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa6df-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa6df-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePinvokeMap (
    [in]  mdToken            tk,
    [in]  DWORD              dwMappingFlags,
    [in]  LPCWSTR            szImportName,
    [in]  mdModuleRef        mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa6df-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fa6df-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="fa6df-106">окне Токен для целевого метода.</span><span class="sxs-lookup"><span data-stu-id="fa6df-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="fa6df-107">окне Флаги, используемые PInvoke для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="fa6df-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="fa6df-108">окне Имя целевого метода экспорта в неуправляемой библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="fa6df-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="fa6df-109">окне Токен для собственной DLL-библиотеки целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="fa6df-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa6df-110">Требования</span><span class="sxs-lookup"><span data-stu-id="fa6df-110">Requirements</span></span>  
 <span data-ttu-id="fa6df-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa6df-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa6df-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="fa6df-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa6df-113">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fa6df-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa6df-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa6df-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa6df-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="fa6df-115">See also</span></span>

- [<span data-ttu-id="fa6df-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="fa6df-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="fa6df-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="fa6df-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
