---
title: Служба
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: aa4eecbcc8a2ef818cd99d777b0e3c2f1f222e46
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273286"
---
# <a name="service"></a><span data-ttu-id="43966-102">Служба</span><span class="sxs-lookup"><span data-stu-id="43966-102">Service</span></span>

<span data-ttu-id="43966-103">Служба</span><span class="sxs-lookup"><span data-stu-id="43966-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43966-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43966-104">Syntax</span></span>  
  
```csharp
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="43966-105">Методы</span><span class="sxs-lookup"><span data-stu-id="43966-105">Methods</span></span>  

 <span data-ttu-id="43966-106">Класс Service не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="43966-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="43966-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="43966-107">Properties</span></span>  

 <span data-ttu-id="43966-108">Класс Service имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="43966-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="43966-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="43966-109">BaseAddresses</span></span>  

 <span data-ttu-id="43966-110">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="43966-110">Data type: string array</span></span>  
  
 <span data-ttu-id="43966-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="43966-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="43966-112">Базовые адреса, используемые службой.</span><span class="sxs-lookup"><span data-stu-id="43966-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="43966-113">Расширения функциональности</span><span class="sxs-lookup"><span data-stu-id="43966-113">Behaviors</span></span>  

 <span data-ttu-id="43966-114">Тип данных: массив Behavior</span><span class="sxs-lookup"><span data-stu-id="43966-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="43966-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="43966-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="43966-116">Поведения, связанные с этой службой.</span><span class="sxs-lookup"><span data-stu-id="43966-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="43966-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="43966-117">ConfigurationName</span></span>  

 <span data-ttu-id="43966-118">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="43966-118">Data type: string</span></span>  
  
 <span data-ttu-id="43966-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="43966-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="43966-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="43966-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="43966-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="43966-121">CounterInstanceName</span></span>  

 <span data-ttu-id="43966-122">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="43966-122">Data type: string</span></span>  
  
 <span data-ttu-id="43966-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="43966-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="43966-124">Имя экземпляра счетчиков производительности службы.</span><span class="sxs-lookup"><span data-stu-id="43966-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="43966-125">Различающееся имя.</span><span class="sxs-lookup"><span data-stu-id="43966-125">DistinguishedName</span></span>  

 <span data-ttu-id="43966-126">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="43966-126">Data type: string</span></span>  
  
 <span data-ttu-id="43966-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="43966-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="43966-128">Имя службы по адресу.</span><span class="sxs-lookup"><span data-stu-id="43966-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="43966-129">Расширения</span><span class="sxs-lookup"><span data-stu-id="43966-129">Extensions</span></span>  

 <span data-ttu-id="43966-130">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="43966-130">Data type: string array</span></span>  
  
 <span data-ttu-id="43966-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="43966-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="43966-132">Контексты экземпляра для расширений экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="43966-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="43966-133">Метаданные</span><span class="sxs-lookup"><span data-stu-id="43966-133">Metadata</span></span>  

 <span data-ttu-id="43966-134">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="43966-134">Data type: string array</span></span>  
  
 <span data-ttu-id="43966-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="43966-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="43966-136">Параметры метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="43966-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="43966-137">name</span><span class="sxs-lookup"><span data-stu-id="43966-137">Name</span></span>  

 <span data-ttu-id="43966-138">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="43966-138">Data type: string</span></span>  
  
 <span data-ttu-id="43966-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="43966-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="43966-140">Уникальное имя службы.</span><span class="sxs-lookup"><span data-stu-id="43966-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="43966-141">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="43966-141">Namespace</span></span>  

 <span data-ttu-id="43966-142">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="43966-142">Data type: string</span></span>  
  
 <span data-ttu-id="43966-143">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="43966-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="43966-144">Пространство имен службы.</span><span class="sxs-lookup"><span data-stu-id="43966-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="43966-145">Opened (Открыто)</span><span class="sxs-lookup"><span data-stu-id="43966-145">Opened</span></span>  

 <span data-ttu-id="43966-146">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="43966-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="43966-147">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="43966-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="43966-148">Время открытия службы.</span><span class="sxs-lookup"><span data-stu-id="43966-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="43966-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="43966-149">OutgoingChannels</span></span>  

 <span data-ttu-id="43966-150">Тип данных: массив Channel</span><span class="sxs-lookup"><span data-stu-id="43966-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="43966-151">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="43966-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="43966-152">Каналы, исходящие из экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="43966-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="43966-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="43966-153">ProcessId</span></span>  

 <span data-ttu-id="43966-154">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="43966-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="43966-155">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="43966-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="43966-156">Возвращает ИД процесса, который размещает службу.</span><span class="sxs-lookup"><span data-stu-id="43966-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43966-157">Требования</span><span class="sxs-lookup"><span data-stu-id="43966-157">Requirements</span></span>  
  
|<span data-ttu-id="43966-158">MOF</span><span class="sxs-lookup"><span data-stu-id="43966-158">MOF</span></span>|<span data-ttu-id="43966-159">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="43966-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="43966-160">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="43966-160">Namespace</span></span>|<span data-ttu-id="43966-161">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="43966-161">Defined in root\ServiceModel</span></span>|
