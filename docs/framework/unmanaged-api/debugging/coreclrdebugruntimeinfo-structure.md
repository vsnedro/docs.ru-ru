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
ms.openlocfilehash: 2c41e7db32ee8557a6c03217b95fd5b040655c70
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860929"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="f27de-102">Структура CoreClrDebugRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="f27de-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="f27de-103">Представляет экземпляр среды CLR, который загружается в процессе на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f27de-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f27de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f27de-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="f27de-105">Члены</span><span class="sxs-lookup"><span data-stu-id="f27de-105">Members</span></span>  
  
|<span data-ttu-id="f27de-106">Участник</span><span class="sxs-lookup"><span data-stu-id="f27de-106">Member</span></span>|<span data-ttu-id="f27de-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f27de-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="f27de-108">Идентификатор среды выполнения, назначаемый прокси-сервером удаленной отладки, работающим на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="f27de-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f27de-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f27de-109">Requirements</span></span>  
 <span data-ttu-id="f27de-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f27de-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f27de-111">**Заголовок:** Кореклрремотедебуггингинтерфацес. h</span><span class="sxs-lookup"><span data-stu-id="f27de-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="f27de-112">**Библиотека:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="f27de-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="f27de-113">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="f27de-113">**.NET Framework Versions:** 3.5 SP1</span></span>
