---
title: Функция CreateICeeFileGen
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
ms.openlocfilehash: 294b82efd66704014aab1b73171afe9165f17664
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616454"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="420fc-102">Функция CreateICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="420fc-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="420fc-103">Создает объект [ицеефилежен](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="420fc-103">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="420fc-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="420fc-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="420fc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="420fc-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="420fc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="420fc-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="420fc-107">заполняет Указатель на адрес нового `ICeeFileGen` объекта.</span><span class="sxs-lookup"><span data-stu-id="420fc-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="420fc-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="420fc-108">Return Value</span></span>  
 <span data-ttu-id="420fc-109">Этот метод возвращает стандартные коды ошибок COM.</span><span class="sxs-lookup"><span data-stu-id="420fc-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="420fc-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="420fc-110">Remarks</span></span>  
 <span data-ttu-id="420fc-111">`ICeeFileGen`Объект используется для создания переносимых исполняемых (PE) файлов среды CLR.</span><span class="sxs-lookup"><span data-stu-id="420fc-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="420fc-112">Вызовите функцию [дестройицеефилежен](destroyiceefilegen-function.md) , чтобы уничтожить `ICeeFileGen` объект после завершения.</span><span class="sxs-lookup"><span data-stu-id="420fc-112">Call the [DestroyICeeFileGen](destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="420fc-113">Требования</span><span class="sxs-lookup"><span data-stu-id="420fc-113">Requirements</span></span>  
 <span data-ttu-id="420fc-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="420fc-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="420fc-115">**Заголовок:** Ицеефилежен. h</span><span class="sxs-lookup"><span data-stu-id="420fc-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="420fc-116">**Библиотека:** Мскорпе. dll</span><span class="sxs-lookup"><span data-stu-id="420fc-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="420fc-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="420fc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="420fc-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="420fc-118">See also</span></span>

- [<span data-ttu-id="420fc-119">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="420fc-119">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
