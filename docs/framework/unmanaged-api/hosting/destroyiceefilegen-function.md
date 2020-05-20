---
title: Функция DestroyICeeFileGen
ms.date: 03/30/2017
api_name:
- DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- DestroyICeeFileGen
helpviewer_keywords:
- DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type:
- apiref
ms.openlocfilehash: ff7e7b299d185b8db263d2076c1e075b87b487fc
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616402"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="84e95-102">Функция DestroyICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="84e95-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="84e95-103">Уничтожает объект [ицеефилежен](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="84e95-103">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="84e95-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="84e95-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84e95-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84e95-105">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84e95-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="84e95-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="84e95-107">окне `ICeeFileGen`Объект для уничтожения.</span><span class="sxs-lookup"><span data-stu-id="84e95-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84e95-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="84e95-108">Return Value</span></span>  
 <span data-ttu-id="84e95-109">Этот метод возвращает стандартные коды ошибок COM.</span><span class="sxs-lookup"><span data-stu-id="84e95-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84e95-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="84e95-110">Remarks</span></span>  
 <span data-ttu-id="84e95-111">`DestroyICeeFileGen`уничтожает `ICeeFileGen` объект, созданный функцией [креатеицеефилежен](createiceefilegen-function.md) .</span><span class="sxs-lookup"><span data-stu-id="84e95-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84e95-112">Требования</span><span class="sxs-lookup"><span data-stu-id="84e95-112">Requirements</span></span>  
 <span data-ttu-id="84e95-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84e95-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84e95-114">**Заголовок:** Ицеефилежен. h</span><span class="sxs-lookup"><span data-stu-id="84e95-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="84e95-115">**Библиотека:** Мскорпе. dll</span><span class="sxs-lookup"><span data-stu-id="84e95-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="84e95-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84e95-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84e95-117">См. также статью</span><span class="sxs-lookup"><span data-stu-id="84e95-117">See also</span></span>

- [<span data-ttu-id="84e95-118">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="84e95-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
