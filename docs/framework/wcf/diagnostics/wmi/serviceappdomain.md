---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 243c9112dd9caf5c92ef77aa0f45b4b1e71a4e9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273260"
---
# <a name="serviceappdomain"></a><span data-ttu-id="77874-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="77874-102">ServiceAppDomain</span></span>

<span data-ttu-id="77874-103">Сопоставляет службу с доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="77874-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77874-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="77874-104">Syntax</span></span>  
  
```csharp
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="77874-105">Методы</span><span class="sxs-lookup"><span data-stu-id="77874-105">Methods</span></span>  

 <span data-ttu-id="77874-106">Класс ServiceAppDomain не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="77874-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="77874-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="77874-107">Properties</span></span>  

 <span data-ttu-id="77874-108">Класс ServiceAppDomain имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="77874-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="77874-109">ref</span><span class="sxs-lookup"><span data-stu-id="77874-109">ref</span></span>  

 <span data-ttu-id="77874-110">Тип данных: Service</span><span class="sxs-lookup"><span data-stu-id="77874-110">Data type: Service</span></span>  
<span data-ttu-id="77874-111">Квалификаторы: ключ</span><span class="sxs-lookup"><span data-stu-id="77874-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="77874-112">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="77874-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="77874-113">Служба этого домена приложения.</span><span class="sxs-lookup"><span data-stu-id="77874-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="77874-114">ref</span><span class="sxs-lookup"><span data-stu-id="77874-114">ref</span></span>  

 <span data-ttu-id="77874-115">Тип данных: AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="77874-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="77874-116">Квалификаторы: ключ</span><span class="sxs-lookup"><span data-stu-id="77874-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="77874-117">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="77874-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="77874-118">Содержит свойства домена приложения.</span><span class="sxs-lookup"><span data-stu-id="77874-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77874-119">Требования</span><span class="sxs-lookup"><span data-stu-id="77874-119">Requirements</span></span>  
  
|<span data-ttu-id="77874-120">MOF</span><span class="sxs-lookup"><span data-stu-id="77874-120">MOF</span></span>|<span data-ttu-id="77874-121">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="77874-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="77874-122">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="77874-122">Namespace</span></span>|<span data-ttu-id="77874-123">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="77874-123">Defined in root\ServiceModel</span></span>|
