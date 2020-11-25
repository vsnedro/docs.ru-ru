---
title: Структура CoreClrDebugRuntimeInfo
ms.date: 03/30/2017
api_name:
- CoreClrDebugRuntimeInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugRuntimeInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreDebugRuntimeInfo structure
- Silverlight, remote debugging
ms.assetid: bd01c30f-b7a8-4179-9497-622b6599b1a6
topic_type:
- apiref
ms.openlocfilehash: 3cc9a1cfb26a784c32d66168bb01d41f91dd5f66
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722388"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="63ac8-102">Структура CoreClrDebugRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="63ac8-102">CoreClrDebugRuntimeInfo Structure</span></span>

<span data-ttu-id="63ac8-103">Представляет экземпляр среды CLR, который загружается в процессе на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="63ac8-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63ac8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63ac8-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="63ac8-105">Члены</span><span class="sxs-lookup"><span data-stu-id="63ac8-105">Members</span></span>  
  
|<span data-ttu-id="63ac8-106">Член</span><span class="sxs-lookup"><span data-stu-id="63ac8-106">Member</span></span>|<span data-ttu-id="63ac8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="63ac8-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="63ac8-108">Идентификатор среды выполнения, назначаемый прокси-сервером удаленной отладки, работающим на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="63ac8-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63ac8-109">Требования</span><span class="sxs-lookup"><span data-stu-id="63ac8-109">Requirements</span></span>  

 <span data-ttu-id="63ac8-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63ac8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63ac8-111">**Заголовок:** Кореклрремотедебуггингинтерфацес. h</span><span class="sxs-lookup"><span data-stu-id="63ac8-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="63ac8-112">**Библиотека:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="63ac8-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="63ac8-113">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="63ac8-113">**.NET Framework Versions:** 3.5 SP1</span></span>
