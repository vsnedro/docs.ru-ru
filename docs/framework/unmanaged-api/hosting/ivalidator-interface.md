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
ms.openlocfilehash: d8e5ab607f9310341ded482b35f02f3845926328
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008564"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="b1b2a-102">Интерфейс IValidator</span><span class="sxs-lookup"><span data-stu-id="b1b2a-102">IValidator Interface</span></span>
<span data-ttu-id="b1b2a-103">Предоставляет методы для проверки переносимых исполняемых (PE) образов и создания отчетов об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="b1b2a-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b1b2a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b1b2a-104">Methods</span></span>  
  
|<span data-ttu-id="b1b2a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b1b2a-105">Method</span></span>|<span data-ttu-id="b1b2a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b1b2a-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b1b2a-107">Проверить</span><span class="sxs-lookup"><span data-stu-id="b1b2a-107">Validate</span></span>|<span data-ttu-id="b1b2a-108">Проверяет указанный PE-файл или промежуточный язык MSIL.</span><span class="sxs-lookup"><span data-stu-id="b1b2a-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="b1b2a-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="b1b2a-109">FormatEventInfo</span></span>|<span data-ttu-id="b1b2a-110">Возвращает сообщение об ошибке, соответствующее указанной ошибке проверки.</span><span class="sxs-lookup"><span data-stu-id="b1b2a-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b1b2a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b1b2a-111">Requirements</span></span>  
 <span data-ttu-id="b1b2a-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1b2a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1b2a-113">**Заголовок:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="b1b2a-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="b1b2a-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b1b2a-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b1b2a-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1b2a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1b2a-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="b1b2a-116">See also</span></span>

- [<span data-ttu-id="b1b2a-117">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="b1b2a-117">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="b1b2a-118">Компонентный класс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b1b2a-118">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
