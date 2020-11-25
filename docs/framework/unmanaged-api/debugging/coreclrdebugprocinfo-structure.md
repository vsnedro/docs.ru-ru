---
title: Структура CoreClrDebugProcInfo
ms.date: 03/30/2017
api_name:
- CoreClrDebugProcInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type:
- apiref
ms.openlocfilehash: 5996393fd1a0504f9c3d3f9f07aa0e3d886a0787
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719701"
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="628ae-102">Структура CoreClrDebugProcInfo</span><span class="sxs-lookup"><span data-stu-id="628ae-102">CoreClrDebugProcInfo Structure</span></span>

<span data-ttu-id="628ae-103">Представляет процесс, который выполняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="628ae-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="628ae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="628ae-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="628ae-105">Члены</span><span class="sxs-lookup"><span data-stu-id="628ae-105">Members</span></span>  
  
|<span data-ttu-id="628ae-106">Член</span><span class="sxs-lookup"><span data-stu-id="628ae-106">Member</span></span>|<span data-ttu-id="628ae-107">Описание</span><span class="sxs-lookup"><span data-stu-id="628ae-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="628ae-108">Идентификатор процесса, назначенный операционной системой.</span><span class="sxs-lookup"><span data-stu-id="628ae-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="628ae-109">Идентификатор процесса, назначенный прокси-сервером удаленной отладки, работающим на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="628ae-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="628ae-110">Этот идентификатор перезапускается реже, чем идентификатор ОС.</span><span class="sxs-lookup"><span data-stu-id="628ae-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="628ae-111">Командная строка процесса.</span><span class="sxs-lookup"><span data-stu-id="628ae-111">Command-line of the process.</span></span> <span data-ttu-id="628ae-112">Этот член может быть усечен.</span><span class="sxs-lookup"><span data-stu-id="628ae-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="628ae-113">Требования</span><span class="sxs-lookup"><span data-stu-id="628ae-113">Requirements</span></span>  

 <span data-ttu-id="628ae-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="628ae-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="628ae-115">**Заголовок:** Кореклрремотедебуггингинтерфацес. h</span><span class="sxs-lookup"><span data-stu-id="628ae-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="628ae-116">**Библиотека:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="628ae-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="628ae-117">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="628ae-117">**.NET Framework Versions:** 3.5 SP1</span></span>
