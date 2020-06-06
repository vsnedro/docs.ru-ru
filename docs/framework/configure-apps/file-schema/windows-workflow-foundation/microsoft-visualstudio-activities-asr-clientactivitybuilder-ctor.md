---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.date: 03/30/2017
ms.topic: reference
api_name:
- Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location:
- Microsoft.VisualStudio.Activities.dll
api_type:
- Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
ms.openlocfilehash: 99f2eb9447bdf43cb57cfe86f35d2c09044ed470
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "69947619"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="2d937-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="2d937-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="2d937-103">Создает экземпляр класса [Microsoft. VisualStudio. activitys. ASR. клиентактивитибуилдер](microsoft-visualstudio-activities-asr-clientactivitybuilder.md) .</span><span class="sxs-lookup"><span data-stu-id="2d937-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d937-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d937-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d937-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2d937-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="2d937-106">Значения параметров</span><span class="sxs-lookup"><span data-stu-id="2d937-106">Parameter Values</span></span>  
 <span data-ttu-id="2d937-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="2d937-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="2d937-108">описывает операцию, выполняемую в создаваемом действии рабочего процесса. Содержит имя операции, тип возвращаемого значения и сведения о параметрах.</span><span class="sxs-lookup"><span data-stu-id="2d937-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="2d937-109">Значение этого параметра не должно быть **равно NULL**.</span><span class="sxs-lookup"><span data-stu-id="2d937-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="2d937-110">Он должен описывать синхронную операцию, в которой используется данный контракт сообщений и принимается аргумент с одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="2d937-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="2d937-111">Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.</span><span class="sxs-lookup"><span data-stu-id="2d937-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="2d937-112">*Указав*</span><span class="sxs-lookup"><span data-stu-id="2d937-112">*configurationName*</span></span>  
  
 <span data-ttu-id="2d937-113">указывает имя конфигурации конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2d937-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="2d937-114">Значение этого параметра не должно быть **null** или пустым.</span><span class="sxs-lookup"><span data-stu-id="2d937-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="2d937-115">Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.</span><span class="sxs-lookup"><span data-stu-id="2d937-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="2d937-116">*проксинамеспаце*</span><span class="sxs-lookup"><span data-stu-id="2d937-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="2d937-117">указывает пространство имен службы для операции.</span><span class="sxs-lookup"><span data-stu-id="2d937-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="2d937-118">Значение этого параметра не должно быть **null** или пустым.</span><span class="sxs-lookup"><span data-stu-id="2d937-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="2d937-119">Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.</span><span class="sxs-lookup"><span data-stu-id="2d937-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d937-120">См. также</span><span class="sxs-lookup"><span data-stu-id="2d937-120">See also</span></span>

- [<span data-ttu-id="2d937-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="2d937-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
