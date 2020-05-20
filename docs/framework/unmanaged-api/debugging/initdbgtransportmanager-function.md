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
ms.openlocfilehash: e18ceb25b9c58a9710ef967cb071e3ef55beea8c
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421050"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="13425-102">Функция InitDbgTransportManager</span><span class="sxs-lookup"><span data-stu-id="13425-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="13425-103">Инициализирует диспетчер транспорта для подключения к удаленному целевому объекту для процесса и перечисления среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="13425-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13425-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13425-104">Syntax</span></span>  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="13425-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="13425-105">Return Value</span></span>  
 <span data-ttu-id="13425-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="13425-106">S_OK</span></span>  
 <span data-ttu-id="13425-107">Успешно.</span><span class="sxs-lookup"><span data-stu-id="13425-107">Success.</span></span>  
  
 <span data-ttu-id="13425-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="13425-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="13425-109">Функции не удалось выделить память для диспетчера транспорта.</span><span class="sxs-lookup"><span data-stu-id="13425-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="13425-110">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="13425-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="13425-111">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="13425-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13425-112">Требования</span><span class="sxs-lookup"><span data-stu-id="13425-112">Requirements</span></span>  
 <span data-ttu-id="13425-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13425-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13425-114">**Заголовок:** Кореклрремотедебуггингинтерфацес. h</span><span class="sxs-lookup"><span data-stu-id="13425-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="13425-115">**Библиотека:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="13425-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="13425-116">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="13425-116">**.NET Framework Versions:** 3.5 SP1</span></span>
