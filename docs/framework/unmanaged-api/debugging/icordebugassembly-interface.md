---
title: Интерфейс ICorDebugAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
ms.openlocfilehash: d9e2236b944137de82bb056820f81014febfcc5f
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894898"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="5ffdf-102">Интерфейс ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="5ffdf-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="5ffdf-103">Представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5ffdf-104">Методы</span><span class="sxs-lookup"><span data-stu-id="5ffdf-104">Methods</span></span>  
  
|<span data-ttu-id="5ffdf-105">Метод</span><span class="sxs-lookup"><span data-stu-id="5ffdf-105">Method</span></span>|<span data-ttu-id="5ffdf-106">Описание</span><span class="sxs-lookup"><span data-stu-id="5ffdf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5ffdf-107">Метод EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="5ffdf-107">EnumerateModules Method</span></span>](icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="5ffdf-108">Возвращает перечислитель для модулей, содержащихся в сборке.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="5ffdf-109">Метод GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="5ffdf-109">GetAppDomain Method</span></span>](icordebugassembly-getappdomain-method.md)|<span data-ttu-id="5ffdf-110">Возвращает указатель интерфейса на домен приложения, содержащий данный `ICorDebugAssembly` экземпляр.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="5ffdf-111">Метод GetCodeBase</span><span class="sxs-lookup"><span data-stu-id="5ffdf-111">GetCodeBase Method</span></span>](icordebugassembly-getcodebase-method.md)|<span data-ttu-id="5ffdf-112">Не реализовано в текущей версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="5ffdf-113">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="5ffdf-113">GetName Method</span></span>](icordebugassembly-getname-method.md)|<span data-ttu-id="5ffdf-114">Возвращает имя сборки.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="5ffdf-115">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="5ffdf-115">GetProcess Method</span></span>](icordebugassembly-getprocess-method.md)|<span data-ttu-id="5ffdf-116">Возвращает экземпляр ICorDebugProcess, в котором выполняется сборка.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ffdf-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="5ffdf-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5ffdf-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ffdf-119">Требования</span><span class="sxs-lookup"><span data-stu-id="5ffdf-119">Requirements</span></span>  
 <span data-ttu-id="5ffdf-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ffdf-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ffdf-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ffdf-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ffdf-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ffdf-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ffdf-123">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ffdf-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ffdf-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5ffdf-124">See also</span></span>

- [<span data-ttu-id="5ffdf-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5ffdf-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
