---
title: Метод EndMerge
ms.date: 03/30/2017
api_name:
- IALink.EndMerge
- EndMerge
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EndMerge
helpviewer_keywords:
- EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type:
- apiref
ms.openlocfilehash: ed4ac7b12caa0dd78b79554258de62b8752553e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684932"
---
# <a name="endmerge-method"></a><span data-ttu-id="3086d-102">Метод EndMerge</span><span class="sxs-lookup"><span data-stu-id="3086d-102">EndMerge Method</span></span>

<span data-ttu-id="3086d-103">Указывает, что все пользовательские атрибуты были объединены в область действия Emit.</span><span class="sxs-lookup"><span data-stu-id="3086d-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3086d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3086d-104">Syntax</span></span>  
  
```cpp  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3086d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3086d-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="3086d-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="3086d-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3086d-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3086d-107">Return Value</span></span>  

 <span data-ttu-id="3086d-108">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="3086d-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3086d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="3086d-109">Requirements</span></span>  

 <span data-ttu-id="3086d-110">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="3086d-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3086d-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3086d-111">See also</span></span>

- [<span data-ttu-id="3086d-112">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="3086d-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3086d-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="3086d-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3086d-114">API ALink</span><span class="sxs-lookup"><span data-stu-id="3086d-114">ALink API</span></span>](index.md)
