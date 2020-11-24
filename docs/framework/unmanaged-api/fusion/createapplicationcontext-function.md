---
title: Функция CreateApplicationContext
ms.date: 03/30/2017
api_name:
- CreateApplicationContext
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateApplicationContext
helpviewer_keywords:
- CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type:
- apiref
ms.openlocfilehash: 9418be85f5b72bac8eed7f5ea4af4fc42439b01f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683239"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="3e6ae-102">Функция CreateApplicationContext</span><span class="sxs-lookup"><span data-stu-id="3e6ae-102">CreateApplicationContext Function</span></span>

<span data-ttu-id="3e6ae-103">Эта функция поддерживает .NET Frameworkную инфраструктуру и не предназначена для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="3e6ae-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e6ae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e6ae-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e6ae-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3e6ae-105">Parameters</span></span>  

 `pName`  
 <span data-ttu-id="3e6ae-106">окне Указатель на понятное имя.</span><span class="sxs-lookup"><span data-stu-id="3e6ae-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="3e6ae-107">заполняет Указатель на контекст приложения.</span><span class="sxs-lookup"><span data-stu-id="3e6ae-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e6ae-108">Требования</span><span class="sxs-lookup"><span data-stu-id="3e6ae-108">Requirements</span></span>  

 <span data-ttu-id="3e6ae-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e6ae-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e6ae-110">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="3e6ae-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3e6ae-111">**Библиотека:** Включается в качестве ресурса в Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="3e6ae-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="3e6ae-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e6ae-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e6ae-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3e6ae-113">See also</span></span>

- [<span data-ttu-id="3e6ae-114">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="3e6ae-114">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="3e6ae-115">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="3e6ae-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="3e6ae-116">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="3e6ae-116">Global Assembly Cache</span></span>](../../app-domains/gac.md)
