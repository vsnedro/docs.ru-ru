---
title: Функция InitDbgTransportManager
ms.date: 03/30/2017
api_name:
- InitDbgTransportManager
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- InitDbgTransportManager
helpviewer_keywords:
- remote debugging API [Silverlight]
- InitDbgTransportManager function
- Silverlight, remote debugging
ms.assetid: a30102ff-c52e-48c9-b3a9-aa14286a42b2
topic_type:
- apiref
ms.openlocfilehash: a5b4783eadb8045733b9ebd6d10c4e31f7829498
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716685"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="2413d-102">Функция InitDbgTransportManager</span><span class="sxs-lookup"><span data-stu-id="2413d-102">InitDbgTransportManager Function</span></span>

<span data-ttu-id="2413d-103">Инициализирует диспетчер транспорта для подключения к удаленному целевому объекту для процесса и перечисления среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2413d-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2413d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2413d-104">Syntax</span></span>  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2413d-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2413d-105">Return Value</span></span>  

 <span data-ttu-id="2413d-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="2413d-106">S_OK</span></span>  
 <span data-ttu-id="2413d-107">Успешно.</span><span class="sxs-lookup"><span data-stu-id="2413d-107">Success.</span></span>  
  
 <span data-ttu-id="2413d-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2413d-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="2413d-109">Функции не удалось выделить память для диспетчера транспорта.</span><span class="sxs-lookup"><span data-stu-id="2413d-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="2413d-110">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="2413d-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="2413d-111">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="2413d-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2413d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="2413d-112">Requirements</span></span>  

 <span data-ttu-id="2413d-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2413d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2413d-114">**Заголовок:** Кореклрремотедебуггингинтерфацес. h</span><span class="sxs-lookup"><span data-stu-id="2413d-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="2413d-115">**Библиотека:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="2413d-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="2413d-116">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="2413d-116">**.NET Framework Versions:** 3.5 SP1</span></span>
