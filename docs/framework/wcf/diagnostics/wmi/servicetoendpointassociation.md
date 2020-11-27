---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 6e20556541b1aa48e7dfc6a8cde97e1bc477457e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273949"
---
# <a name="servicetoendpointassociation"></a><span data-ttu-id="67adc-102">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="67adc-102">ServiceToEndpointAssociation</span></span>

<span data-ttu-id="67adc-103">Сопоставляет службу конечной точке.</span><span class="sxs-lookup"><span data-stu-id="67adc-103">Maps a service to an endpoint.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67adc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67adc-104">Syntax</span></span>  
  
```csharp
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="67adc-105">Методы</span><span class="sxs-lookup"><span data-stu-id="67adc-105">Methods</span></span>  

 <span data-ttu-id="67adc-106">Класс ServiceToEndpointAssociation не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="67adc-106">The ServiceToEndpointAssociation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="67adc-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="67adc-107">Properties</span></span>  

 <span data-ttu-id="67adc-108">Класс ServiceToEndpointAssociation имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="67adc-108">The ServiceToEndpointAssociation class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="67adc-109">ref</span><span class="sxs-lookup"><span data-stu-id="67adc-109">ref</span></span>  

 <span data-ttu-id="67adc-110">Тип данных: Service</span><span class="sxs-lookup"><span data-stu-id="67adc-110">Data type: Service</span></span>  
  
 <span data-ttu-id="67adc-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="67adc-111">Access type: Read-only</span></span>  
<span data-ttu-id="67adc-112">Квалификаторы: ключ</span><span class="sxs-lookup"><span data-stu-id="67adc-112">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="67adc-113">Служба, связанная с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="67adc-113">The service associated with the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="67adc-114">ref</span><span class="sxs-lookup"><span data-stu-id="67adc-114">ref</span></span>  

 <span data-ttu-id="67adc-115">Тип данных: Endpoint</span><span class="sxs-lookup"><span data-stu-id="67adc-115">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="67adc-116">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="67adc-116">Access type: Read-only</span></span>  
<span data-ttu-id="67adc-117">Квалификаторы: ключ</span><span class="sxs-lookup"><span data-stu-id="67adc-117">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="67adc-118">Конечная точка, связанная со службой.</span><span class="sxs-lookup"><span data-stu-id="67adc-118">The endpoint associated with the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67adc-119">Требования</span><span class="sxs-lookup"><span data-stu-id="67adc-119">Requirements</span></span>  
  
|<span data-ttu-id="67adc-120">MOF</span><span class="sxs-lookup"><span data-stu-id="67adc-120">MOF</span></span>|<span data-ttu-id="67adc-121">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="67adc-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="67adc-122">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="67adc-122">Namespace</span></span>|<span data-ttu-id="67adc-123">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="67adc-123">Defined in root\ServiceModel</span></span>|
