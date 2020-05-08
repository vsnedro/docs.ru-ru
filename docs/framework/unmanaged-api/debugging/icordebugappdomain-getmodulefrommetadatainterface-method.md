---
title: Метод ICorDebugAppDomain::GetModuleFromMetaDataInterface
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetModuleFromMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDataInterface
helpviewer_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDatainterface method [.NET Framework debugging]
- GetModuleFromMetaDatainterface method [.NET Framework debugging]
ms.assetid: f35225b3-5dda-4d5a-913d-b3373e9ab81e
topic_type:
- apiref
ms.openlocfilehash: f317eb1b3d91fc005d59d6a06bad329a5f68aa11
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895229"
---
# <a name="icordebugappdomaingetmodulefrommetadatainterface-method"></a><span data-ttu-id="4f24f-102">Метод ICorDebugAppDomain::GetModuleFromMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="4f24f-102">ICorDebugAppDomain::GetModuleFromMetaDataInterface Method</span></span>
<span data-ttu-id="4f24f-103">Возвращает модуль, соответствующий заданному интерфейсу метаданных.</span><span class="sxs-lookup"><span data-stu-id="4f24f-103">Gets the module that corresponds to the given metadata interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f24f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f24f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromMetaDataInterface (  
    [in] IUnknown           *pIMetaData,  
    [out] ICorDebugModule  **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f24f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f24f-105">Parameters</span></span>  
 `pIMetaData`  
 <span data-ttu-id="4f24f-106">окне Указатель на объект, который является одним из [интерфейсов метаданных](../metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="4f24f-106">[in] A pointer to an object that is one of the [Metadata interfaces](../metadata/metadata-interfaces.md).</span></span>  
  
 `ppModule`  
 <span data-ttu-id="4f24f-107">заполняет Указатель на адрес объекта ICorDebugModule, который представляет модуль, соответствующий заданному интерфейсу метаданных.</span><span class="sxs-lookup"><span data-stu-id="4f24f-107">[out] A pointer to the address of an ICorDebugModule object that represents the module corresponding to the given metadata interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f24f-108">Требования</span><span class="sxs-lookup"><span data-stu-id="4f24f-108">Requirements</span></span>  
 <span data-ttu-id="4f24f-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f24f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f24f-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f24f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f24f-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f24f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f24f-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f24f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
