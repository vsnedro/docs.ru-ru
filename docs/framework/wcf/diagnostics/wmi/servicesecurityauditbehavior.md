---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 9da8f77ee8ea5dc8b22ac5c0cb5113e906c5dc78
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262272"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="3f22c-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="3f22c-102">ServiceSecurityAuditBehavior</span></span>

<span data-ttu-id="3f22c-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="3f22c-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f22c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f22c-104">Syntax</span></span>  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3f22c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="3f22c-105">Methods</span></span>  

 <span data-ttu-id="3f22c-106">Класс ServiceSecurityAuditBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="3f22c-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3f22c-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="3f22c-107">Properties</span></span>  

 <span data-ttu-id="3f22c-108">Класс ServiceSecurityAuditBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="3f22c-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="3f22c-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="3f22c-109">AuditLogLocation</span></span>  

 <span data-ttu-id="3f22c-110">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="3f22c-110">Data type: string</span></span>  
  
 <span data-ttu-id="3f22c-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="3f22c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f22c-112">Местоположение журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="3f22c-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="3f22c-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="3f22c-113">MessageAuthenticationAuditLevel</span></span>  

 <span data-ttu-id="3f22c-114">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="3f22c-114">Data type: string</span></span>  
  
 <span data-ttu-id="3f22c-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="3f22c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f22c-116">Тип уровня проверки подлинности сообщений, используемый для записи в журнал событий аудита.</span><span class="sxs-lookup"><span data-stu-id="3f22c-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="3f22c-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="3f22c-117">ServiceAuthorizationAuditLevel</span></span>  

 <span data-ttu-id="3f22c-118">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="3f22c-118">Data type: string</span></span>  
  
 <span data-ttu-id="3f22c-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="3f22c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f22c-120">Типы событий авторизации, записываемых в журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="3f22c-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="3f22c-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="3f22c-121">SuppressAuditFailure</span></span>  

 <span data-ttu-id="3f22c-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="3f22c-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="3f22c-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="3f22c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f22c-124">Логическое значение, задающее поведение для подавления ошибок записи в журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="3f22c-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f22c-125">Требования</span><span class="sxs-lookup"><span data-stu-id="3f22c-125">Requirements</span></span>  
  
|<span data-ttu-id="3f22c-126">MOF</span><span class="sxs-lookup"><span data-stu-id="3f22c-126">MOF</span></span>|<span data-ttu-id="3f22c-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3f22c-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3f22c-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="3f22c-128">Namespace</span></span>|<span data-ttu-id="3f22c-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="3f22c-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f22c-130">См. также</span><span class="sxs-lookup"><span data-stu-id="3f22c-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
