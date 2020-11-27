---
title: Конечная точка
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: ceb4e4b41502b00d7bb21f1ecbd8249fccf1ce3b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288818"
---
# <a name="endpoint"></a><span data-ttu-id="621b4-102">Конечная точка</span><span class="sxs-lookup"><span data-stu-id="621b4-102">Endpoint</span></span>

<span data-ttu-id="621b4-103">Конечная точка</span><span class="sxs-lookup"><span data-stu-id="621b4-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="621b4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="621b4-104">Syntax</span></span>  
  
```csharp
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="621b4-105">Методы</span><span class="sxs-lookup"><span data-stu-id="621b4-105">Methods</span></span>  

 <span data-ttu-id="621b4-106">Класс Endpoint определяет следующий метод.</span><span class="sxs-lookup"><span data-stu-id="621b4-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="621b4-107">Метод</span><span class="sxs-lookup"><span data-stu-id="621b4-107">Method</span></span>|<span data-ttu-id="621b4-108">Описание</span><span class="sxs-lookup"><span data-stu-id="621b4-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="621b4-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="621b4-109">GetOperationCounterInstanceName</span></span>](getoperationcounterinstancename.md)|<span data-ttu-id="621b4-110">Извлекает имя экземпляра счетчика производительности операций</span><span class="sxs-lookup"><span data-stu-id="621b4-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="621b4-111">Свойства</span><span class="sxs-lookup"><span data-stu-id="621b4-111">Properties</span></span>  

 <span data-ttu-id="621b4-112">Класс Endpoint имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="621b4-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="621b4-113">Адрес</span><span class="sxs-lookup"><span data-stu-id="621b4-113">Address</span></span>  

 <span data-ttu-id="621b4-114">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="621b4-114">Data type: string</span></span>  
  
 <span data-ttu-id="621b4-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="621b4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="621b4-116">Универсальный код ресурса (URI), содержащий адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="621b4-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="621b4-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="621b4-117">AddressHeaders</span></span>  

 <span data-ttu-id="621b4-118">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="621b4-118">Data type: string array</span></span>  
  
 <span data-ttu-id="621b4-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="621b4-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="621b4-120">Коллекция заголовков адреса, прикрепленных к этой конечной точке.</span><span class="sxs-lookup"><span data-stu-id="621b4-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="621b4-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="621b4-121">AddressIdentity</span></span>  

 <span data-ttu-id="621b4-122">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="621b4-122">Data type: string</span></span>  
  
 <span data-ttu-id="621b4-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="621b4-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="621b4-124">Удостоверение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="621b4-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="621b4-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="621b4-125">AppDomainId</span></span>  

 <span data-ttu-id="621b4-126">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="621b4-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="621b4-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="621b4-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="621b4-128">Идентификатор домена приложения, который размещает конечную точку.</span><span class="sxs-lookup"><span data-stu-id="621b4-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="621b4-129">Расширения функциональности</span><span class="sxs-lookup"><span data-stu-id="621b4-129">Behaviors</span></span>  

 <span data-ttu-id="621b4-130">Тип данных: массив Behavior</span><span class="sxs-lookup"><span data-stu-id="621b4-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="621b4-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="621b4-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="621b4-132">Коллекция поведений, реализуемых этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="621b4-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="621b4-133">Привязка</span><span class="sxs-lookup"><span data-stu-id="621b4-133">Binding</span></span>  

 <span data-ttu-id="621b4-134">Тип данных: Binding</span><span class="sxs-lookup"><span data-stu-id="621b4-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="621b4-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="621b4-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="621b4-136">Привязка, используемая этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="621b4-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="621b4-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="621b4-137">ContractName</span></span>  

 <span data-ttu-id="621b4-138">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="621b4-138">Data type: string</span></span>  
  
 <span data-ttu-id="621b4-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="621b4-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="621b4-140">Строка, в которой указывается, какой контракт предоставляется этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="621b4-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="621b4-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="621b4-141">CounterInstanceName</span></span>  

 <span data-ttu-id="621b4-142">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="621b4-142">Data type: string</span></span>  
  
 <span data-ttu-id="621b4-143">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="621b4-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="621b4-144">Имя экземпляра счетчиков производительности конечной точки.</span><span class="sxs-lookup"><span data-stu-id="621b4-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="621b4-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="621b4-145">ListenUri</span></span>  

 <span data-ttu-id="621b4-146">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="621b4-146">Data type: string</span></span>  
  
 <span data-ttu-id="621b4-147">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="621b4-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="621b4-148">Универсальный код ресурса (URI), от которого данная конечная точка ожидает передачи данных.</span><span class="sxs-lookup"><span data-stu-id="621b4-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="621b4-149">name</span><span class="sxs-lookup"><span data-stu-id="621b4-149">Name</span></span>  

 <span data-ttu-id="621b4-150">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="621b4-150">Data type: string</span></span>  
  
 <span data-ttu-id="621b4-151">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="621b4-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="621b4-152">Уникальное имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="621b4-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="621b4-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="621b4-153">ProcessId</span></span>  

 <span data-ttu-id="621b4-154">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="621b4-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="621b4-155">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="621b4-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="621b4-156">Возвращает идентификатор процесса, который размещает конечную точку.</span><span class="sxs-lookup"><span data-stu-id="621b4-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="621b4-157">ref</span><span class="sxs-lookup"><span data-stu-id="621b4-157">ref</span></span>  

 <span data-ttu-id="621b4-158">Тип данных: Contract</span><span class="sxs-lookup"><span data-stu-id="621b4-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="621b4-159">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="621b4-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="621b4-160">Контракт, предоставляемый этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="621b4-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="621b4-161">Требования</span><span class="sxs-lookup"><span data-stu-id="621b4-161">Requirements</span></span>  
  
|<span data-ttu-id="621b4-162">MOF</span><span class="sxs-lookup"><span data-stu-id="621b4-162">MOF</span></span>|<span data-ttu-id="621b4-163">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="621b4-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="621b4-164">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="621b4-164">Namespace</span></span>|<span data-ttu-id="621b4-165">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="621b4-165">Defined in root\ServiceModel</span></span>|
