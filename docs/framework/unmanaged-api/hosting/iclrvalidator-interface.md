---
title: Интерфейс ICLRValidator
ms.date: 03/30/2017
api_name:
- ICLRValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator
helpviewer_keywords:
- ICLRValidator interface [.NET Framework hosting]
ms.assetid: 2edd0a10-77fb-4173-91eb-f2970cc364d0
topic_type:
- apiref
ms.openlocfilehash: d9ccd5c6c91b1ab2166ff40a0fb2048e15927d3a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723952"
---
# <a name="iclrvalidator-interface"></a><span data-ttu-id="50557-102">Интерфейс ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="50557-102">ICLRValidator Interface</span></span>

<span data-ttu-id="50557-103">Предоставляет методы для проверки переносимых исполняемых (PE) образов и создания отчетов об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="50557-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50557-104">Методы</span><span class="sxs-lookup"><span data-stu-id="50557-104">Methods</span></span>  
  
|<span data-ttu-id="50557-105">Метод</span><span class="sxs-lookup"><span data-stu-id="50557-105">Method</span></span>|<span data-ttu-id="50557-106">Описание</span><span class="sxs-lookup"><span data-stu-id="50557-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50557-107">Метод FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="50557-107">FormatEventInfo Method</span></span>](iclrvalidator-formateventinfo-method.md)|<span data-ttu-id="50557-108">Возвращает подробное сообщение об указанной ошибке проверки.</span><span class="sxs-lookup"><span data-stu-id="50557-108">Gets a detailed message about the specified validation error.</span></span>|  
|[<span data-ttu-id="50557-109">Метод Validate</span><span class="sxs-lookup"><span data-stu-id="50557-109">Validate Method</span></span>](iclrvalidator-validate-method.md)|<span data-ttu-id="50557-110">Проверяет переносимый исполняемый файл или язык MSIL в указанном файле.</span><span class="sxs-lookup"><span data-stu-id="50557-110">Validates the portable executable or Microsoft intermediate language (MSIL) in the specified file.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="50557-111">Требования</span><span class="sxs-lookup"><span data-stu-id="50557-111">Requirements</span></span>  

 <span data-ttu-id="50557-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50557-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50557-113">**Заголовок:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="50557-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="50557-114">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="50557-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50557-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50557-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50557-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="50557-116">See also</span></span>

- [<span data-ttu-id="50557-117">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="50557-117">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="50557-118">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="50557-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="50557-119">Кокласс CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="50557-119">CLRRuntimeHost Coclass</span></span>](clrruntimehost-coclass.md)
