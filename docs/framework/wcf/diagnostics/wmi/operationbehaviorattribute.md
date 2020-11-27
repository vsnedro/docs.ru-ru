---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: 76cc619aed4ba2b944a8d11dc454a40368a4068c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269084"
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="d0b1b-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="d0b1b-102">OperationBehaviorAttribute</span></span>

<span data-ttu-id="d0b1b-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="d0b1b-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0b1b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0b1b-104">Syntax</span></span>  
  
```csharp
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d0b1b-105">Методы</span><span class="sxs-lookup"><span data-stu-id="d0b1b-105">Methods</span></span>  

 <span data-ttu-id="d0b1b-106">Класс OperationBehaviorAttribute не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="d0b1b-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d0b1b-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="d0b1b-107">Properties</span></span>  

 <span data-ttu-id="d0b1b-108">Класс OperationBehaviorAttribute имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="d0b1b-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="d0b1b-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="d0b1b-109">AutoDisposeParameters</span></span>  

 <span data-ttu-id="d0b1b-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="d0b1b-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="d0b1b-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d0b1b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0b1b-112">Состояние возможности автоматического удаления для параметров.</span><span class="sxs-lookup"><span data-stu-id="d0b1b-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="d0b1b-113">Олицетворение</span><span class="sxs-lookup"><span data-stu-id="d0b1b-113">Impersonation</span></span>  

 <span data-ttu-id="d0b1b-114">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="d0b1b-114">Data type: string</span></span>  
  
 <span data-ttu-id="d0b1b-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d0b1b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0b1b-116">Указывает уровень олицетворения вызывающей стороны, который поддерживает операция.</span><span class="sxs-lookup"><span data-stu-id="d0b1b-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="d0b1b-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="d0b1b-117">ReleaseInstanceMode</span></span>  

 <span data-ttu-id="d0b1b-118">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="d0b1b-118">Data type: string</span></span>  
  
 <span data-ttu-id="d0b1b-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d0b1b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0b1b-120">Указывает, когда удалять объект в процессе вызова операции.</span><span class="sxs-lookup"><span data-stu-id="d0b1b-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="d0b1b-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="d0b1b-121">TransactionAutoComplete</span></span>  

 <span data-ttu-id="d0b1b-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="d0b1b-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="d0b1b-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d0b1b-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0b1b-124">Указывает, следует ли автоматически фиксировать текущую транзакцию при отсутствии необработанных исключений.</span><span class="sxs-lookup"><span data-stu-id="d0b1b-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="d0b1b-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="d0b1b-125">TransactionScopeRequired</span></span>  

 <span data-ttu-id="d0b1b-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="d0b1b-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="d0b1b-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d0b1b-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0b1b-128">Указывает, требует ли операция транзакции.</span><span class="sxs-lookup"><span data-stu-id="d0b1b-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0b1b-129">Требования</span><span class="sxs-lookup"><span data-stu-id="d0b1b-129">Requirements</span></span>  
  
|<span data-ttu-id="d0b1b-130">MOF</span><span class="sxs-lookup"><span data-stu-id="d0b1b-130">MOF</span></span>|<span data-ttu-id="d0b1b-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d0b1b-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d0b1b-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="d0b1b-132">Namespace</span></span>|<span data-ttu-id="d0b1b-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="d0b1b-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d0b1b-134">См. также</span><span class="sxs-lookup"><span data-stu-id="d0b1b-134">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
