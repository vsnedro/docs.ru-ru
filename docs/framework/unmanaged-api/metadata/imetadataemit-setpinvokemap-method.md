---
title: Метод IMetaDataEmit::SetPinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type:
- apiref
ms.openlocfilehash: 0d34c7a2992a2779b96ec87f1a0175d8fcbce34a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007797"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="9b92e-102">Метод IMetaDataEmit::SetPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="9b92e-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="9b92e-103">Задает или изменяет функции сигнатуры PInvoke метода, как определено в предыдущем вызове [IMetaDataEmit::D ефинепинвокемап](imetadataemit-definepinvokemap-method.md).</span><span class="sxs-lookup"><span data-stu-id="9b92e-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b92e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b92e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (
    [in]  mdToken      tk,
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,
    [in]  mdModuleRef  mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b92e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9b92e-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="9b92e-106">окне Объект, `mdToken` к которому применяются сведения о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="9b92e-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="9b92e-107">окне Флаги, используемые PInvoke для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="9b92e-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="9b92e-108">Это битовая маска `CorPinvokeMap` значений.</span><span class="sxs-lookup"><span data-stu-id="9b92e-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="9b92e-109">окне Имя целевого экспорта в собственной библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="9b92e-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="9b92e-110">окне `mdModuleRef`Маркер для целевой неуправляемой библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="9b92e-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b92e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="9b92e-111">Requirements</span></span>  
 <span data-ttu-id="9b92e-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b92e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b92e-113">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="9b92e-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b92e-114">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9b92e-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b92e-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b92e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b92e-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="9b92e-116">See also</span></span>

- [<span data-ttu-id="9b92e-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="9b92e-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="9b92e-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="9b92e-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
