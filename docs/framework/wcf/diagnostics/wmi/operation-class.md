---
title: Класс операции
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 6b47d933dc84813532398830c92c95210208a709
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269162"
---
# <a name="operation-class"></a><span data-ttu-id="467e4-102">Класс операции</span><span class="sxs-lookup"><span data-stu-id="467e4-102">Operation class</span></span>

<span data-ttu-id="467e4-103">Операция</span><span class="sxs-lookup"><span data-stu-id="467e4-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="467e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="467e4-104">Syntax</span></span>  
  
```csharp
class Operation  
{  
  string Action;  
  boolean AsyncPattern;  
  Behavior Behaviors[];  
  boolean IsCallback;  
  boolean IsInitiating;  
  boolean IsOneWay;  
  boolean IsTerminating;  
  string MethodSignature;  
  string Name;  
  string ParameterTypes[];  
  string ReplyAction;  
  string ReturnType;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="467e4-105">Методы</span><span class="sxs-lookup"><span data-stu-id="467e4-105">Methods</span></span>  

 <span data-ttu-id="467e4-106">Класс Operation не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="467e4-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="467e4-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="467e4-107">Properties</span></span>  

 <span data-ttu-id="467e4-108">Класс Operation имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="467e4-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="467e4-109">Действие</span><span class="sxs-lookup"><span data-stu-id="467e4-109">Action</span></span>  

 <span data-ttu-id="467e4-110">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="467e4-110">Data type: string</span></span>  
  
 <span data-ttu-id="467e4-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="467e4-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="467e4-112">Действие WS-Addressing сообщения запроса.</span><span class="sxs-lookup"><span data-stu-id="467e4-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="467e4-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="467e4-113">AsyncPattern</span></span>  

 <span data-ttu-id="467e4-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="467e4-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="467e4-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="467e4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="467e4-116">Указывает, что операция реализуется асинхронно с помощью `Begin` пары методов [открывающий/закрывающий угловые скобки] и `End` [открывающих и закрывающих угловых скобок] в контракте службы.</span><span class="sxs-lookup"><span data-stu-id="467e4-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="467e4-117">Расширения функциональности</span><span class="sxs-lookup"><span data-stu-id="467e4-117">Behaviors</span></span>  

 <span data-ttu-id="467e4-118">Тип данных: массив Behavior</span><span class="sxs-lookup"><span data-stu-id="467e4-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="467e4-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="467e4-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="467e4-120">Поведения, связанные с этой операцией.</span><span class="sxs-lookup"><span data-stu-id="467e4-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="467e4-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="467e4-121">IsCallback</span></span>  

 <span data-ttu-id="467e4-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="467e4-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="467e4-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="467e4-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="467e4-124">Истинно, если операция является операцией обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="467e4-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="467e4-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="467e4-125">IsInitiating</span></span>  

 <span data-ttu-id="467e4-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="467e4-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="467e4-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="467e4-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="467e4-128">Показывает, реализует ли метод операцию, которая может инициировать сеанс на сервере.</span><span class="sxs-lookup"><span data-stu-id="467e4-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="467e4-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="467e4-129">IsOneWay</span></span>  

 <span data-ttu-id="467e4-130">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="467e4-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="467e4-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="467e4-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="467e4-132">Показывает, возвращает ли операция ответное сообщение.</span><span class="sxs-lookup"><span data-stu-id="467e4-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="467e4-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="467e4-133">IsTerminating</span></span>  

 <span data-ttu-id="467e4-134">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="467e4-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="467e4-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="467e4-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="467e4-136">Показывает, возвращает ли операция ответное сообщение.</span><span class="sxs-lookup"><span data-stu-id="467e4-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="467e4-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="467e4-137">MethodSignature</span></span>  

 <span data-ttu-id="467e4-138">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="467e4-138">Data type: string</span></span>  
  
 <span data-ttu-id="467e4-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="467e4-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="467e4-140">Подпись метода операции.</span><span class="sxs-lookup"><span data-stu-id="467e4-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="467e4-141">name</span><span class="sxs-lookup"><span data-stu-id="467e4-141">Name</span></span>  

 <span data-ttu-id="467e4-142">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="467e4-142">Data type: string</span></span>  
  
 <span data-ttu-id="467e4-143">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="467e4-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="467e4-144">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="467e4-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="467e4-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="467e4-145">ParameterTypes</span></span>  

 <span data-ttu-id="467e4-146">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="467e4-146">Data type: string array</span></span>  
  
 <span data-ttu-id="467e4-147">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="467e4-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="467e4-148">Типы параметров операции.</span><span class="sxs-lookup"><span data-stu-id="467e4-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="467e4-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="467e4-149">ReplyAction</span></span>  

 <span data-ttu-id="467e4-150">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="467e4-150">Data type: string</span></span>  
  
 <span data-ttu-id="467e4-151">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="467e4-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="467e4-152">Значение действия SOAP для ответного сообщения операции.</span><span class="sxs-lookup"><span data-stu-id="467e4-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="467e4-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="467e4-153">ReturnType</span></span>  

 <span data-ttu-id="467e4-154">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="467e4-154">Data type: string</span></span>  
  
 <span data-ttu-id="467e4-155">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="467e4-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="467e4-156">Тип возвращаемого значения операции.</span><span class="sxs-lookup"><span data-stu-id="467e4-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="467e4-157">Требования</span><span class="sxs-lookup"><span data-stu-id="467e4-157">Requirements</span></span>  
  
|<span data-ttu-id="467e4-158">MOF</span><span class="sxs-lookup"><span data-stu-id="467e4-158">MOF</span></span>|<span data-ttu-id="467e4-159">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="467e4-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="467e4-160">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="467e4-160">Namespace</span></span>|<span data-ttu-id="467e4-161">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="467e4-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="467e4-162">См. также</span><span class="sxs-lookup"><span data-stu-id="467e4-162">See also</span></span>

- <xref:System.ServiceModel.Description.OperationDescription>
