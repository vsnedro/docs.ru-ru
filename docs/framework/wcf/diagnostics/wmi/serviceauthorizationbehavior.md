---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: d3625865484568746888ef0638d9a8501e610bef
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273208"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="94750-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="94750-102">ServiceAuthorizationBehavior</span></span>

<span data-ttu-id="94750-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="94750-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94750-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94750-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="94750-105">Методы</span><span class="sxs-lookup"><span data-stu-id="94750-105">Methods</span></span>  

 <span data-ttu-id="94750-106">Класс ServiceAuthorizationBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="94750-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="94750-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="94750-107">Properties</span></span>  

 <span data-ttu-id="94750-108">Класс ServiceAuthorizationBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="94750-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="94750-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="94750-109">ImpersonateCallerForAllOperations</span></span>  

 <span data-ttu-id="94750-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="94750-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="94750-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="94750-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94750-112">Значение, которое определяет, будет ли служба пытаться производить олицетворение при помощи учетных данных, содержащихся во входящем сообщении.</span><span class="sxs-lookup"><span data-stu-id="94750-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="94750-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="94750-113">PrincipalPermissionMode</span></span>  

 <span data-ttu-id="94750-114">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="94750-114">Data type: string</span></span>  
  
 <span data-ttu-id="94750-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="94750-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94750-116">Участник, используемый для выполнения операций на сервере.</span><span class="sxs-lookup"><span data-stu-id="94750-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="94750-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="94750-117">RoleProvider</span></span>  

 <span data-ttu-id="94750-118">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="94750-118">Data type: string</span></span>  
  
 <span data-ttu-id="94750-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="94750-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94750-120">Имя поставщика ролей ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="94750-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="94750-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="94750-121">ServiceAuthorizationManager</span></span>  

 <span data-ttu-id="94750-122">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="94750-122">Data type: string</span></span>  
  
 <span data-ttu-id="94750-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="94750-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94750-124">Диспетчер авторизации, используемый для пользовательской авторизации.</span><span class="sxs-lookup"><span data-stu-id="94750-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94750-125">Требования</span><span class="sxs-lookup"><span data-stu-id="94750-125">Requirements</span></span>  
  
|<span data-ttu-id="94750-126">MOF</span><span class="sxs-lookup"><span data-stu-id="94750-126">MOF</span></span>|<span data-ttu-id="94750-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="94750-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="94750-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="94750-128">Namespace</span></span>|<span data-ttu-id="94750-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="94750-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94750-130">См. также</span><span class="sxs-lookup"><span data-stu-id="94750-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
