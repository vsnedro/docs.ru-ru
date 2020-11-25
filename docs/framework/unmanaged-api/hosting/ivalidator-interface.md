---
title: Интерфейс IValidator
ms.date: 03/30/2017
api_name:
- IValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IValidator
helpviewer_keywords:
- IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type:
- apiref
ms.openlocfilehash: ce417402231d03828243bfb8bb7543c0a644a882
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700994"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="dcc83-102">Интерфейс IValidator</span><span class="sxs-lookup"><span data-stu-id="dcc83-102">IValidator Interface</span></span>

<span data-ttu-id="dcc83-103">Предоставляет методы для проверки переносимых исполняемых (PE) образов и создания отчетов об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="dcc83-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dcc83-104">Методы</span><span class="sxs-lookup"><span data-stu-id="dcc83-104">Methods</span></span>  
  
|<span data-ttu-id="dcc83-105">Метод</span><span class="sxs-lookup"><span data-stu-id="dcc83-105">Method</span></span>|<span data-ttu-id="dcc83-106">Description</span><span class="sxs-lookup"><span data-stu-id="dcc83-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="dcc83-107">Проверить</span><span class="sxs-lookup"><span data-stu-id="dcc83-107">Validate</span></span>|<span data-ttu-id="dcc83-108">Проверяет указанный PE-файл или промежуточный язык MSIL.</span><span class="sxs-lookup"><span data-stu-id="dcc83-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="dcc83-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="dcc83-109">FormatEventInfo</span></span>|<span data-ttu-id="dcc83-110">Возвращает сообщение об ошибке, соответствующее указанной ошибке проверки.</span><span class="sxs-lookup"><span data-stu-id="dcc83-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dcc83-111">Требования</span><span class="sxs-lookup"><span data-stu-id="dcc83-111">Requirements</span></span>  

 <span data-ttu-id="dcc83-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcc83-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcc83-113">**Заголовок:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="dcc83-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="dcc83-114">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dcc83-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dcc83-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcc83-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcc83-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dcc83-116">See also</span></span>

- [<span data-ttu-id="dcc83-117">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="dcc83-117">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="dcc83-118">Компонентный класс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="dcc83-118">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
