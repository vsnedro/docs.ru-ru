---
title: Интерфейс ICLRDebugging
ms.date: 03/30/2017
api_name:
- ICLRDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging
helpviewer_keywords:
- ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type:
- apiref
ms.openlocfilehash: a3d4297e3b16dd1637e6293dbf7f04d4fbeda50f
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860387"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="1f0ec-102">Интерфейс ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="1f0ec-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="1f0ec-103">Предоставляет методы, обрабатывающие загрузку и выгрузку модулей для отладки.</span><span class="sxs-lookup"><span data-stu-id="1f0ec-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1f0ec-104">Методы</span><span class="sxs-lookup"><span data-stu-id="1f0ec-104">Methods</span></span>  
  
|<span data-ttu-id="1f0ec-105">Метод</span><span class="sxs-lookup"><span data-stu-id="1f0ec-105">Method</span></span>|<span data-ttu-id="1f0ec-106">Описание</span><span class="sxs-lookup"><span data-stu-id="1f0ec-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1f0ec-107">Метод OpenVirtualProcess</span><span class="sxs-lookup"><span data-stu-id="1f0ec-107">OpenVirtualProcess Method</span></span>](iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="1f0ec-108">Возвращает интерфейс "ICorDebugProcess", соответствующий модулю среды CLR, загруженному в процессе.</span><span class="sxs-lookup"><span data-stu-id="1f0ec-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="1f0ec-109">Метод CanUnloadNow</span><span class="sxs-lookup"><span data-stu-id="1f0ec-109">CanUnloadNow Method</span></span>](iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="1f0ec-110">Определяет, используется ли по-прежнему Библиотека, предоставленная интерфейсом [иклрдебуггинглибрарипровидер](iclrdebugginglibraryprovider-interface.md) , или она может быть выгружена.</span><span class="sxs-lookup"><span data-stu-id="1f0ec-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f0ec-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="1f0ec-111">Remarks</span></span>  
 <span data-ttu-id="1f0ec-112">Экземпляр `ICLRDebugging` интерфейса можно получить с помощью функции [клркреатеинстанце](../hosting/clrcreateinstance-function.md) .</span><span class="sxs-lookup"><span data-stu-id="1f0ec-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f0ec-113">Требования</span><span class="sxs-lookup"><span data-stu-id="1f0ec-113">Requirements</span></span>  
 <span data-ttu-id="1f0ec-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f0ec-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f0ec-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f0ec-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f0ec-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f0ec-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f0ec-117">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f0ec-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f0ec-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1f0ec-118">See also</span></span>

- [<span data-ttu-id="1f0ec-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1f0ec-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1f0ec-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="1f0ec-120">Debugging</span></span>](index.md)
