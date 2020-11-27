---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d7e89acedc8fc1004b0198172e58813944df85f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262311"
---
# <a name="servicecredentials"></a><span data-ttu-id="4a33b-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="4a33b-102">ServiceCredentials</span></span>

<span data-ttu-id="4a33b-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="4a33b-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a33b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a33b-104">Syntax</span></span>  
  
```csharp
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4a33b-105">Методы</span><span class="sxs-lookup"><span data-stu-id="4a33b-105">Methods</span></span>  

 <span data-ttu-id="4a33b-106">Класс ServiceCredentials не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="4a33b-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4a33b-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="4a33b-107">Properties</span></span>  

 <span data-ttu-id="4a33b-108">Класс ServiceCredentials имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="4a33b-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="4a33b-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="4a33b-109">ClientCertificate</span></span>  

 <span data-ttu-id="4a33b-110">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="4a33b-110">Data type: string</span></span>  
  
 <span data-ttu-id="4a33b-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4a33b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a33b-112">Параметры проверки подлинности сертификата клиента и подготовки для этой службы.</span><span class="sxs-lookup"><span data-stu-id="4a33b-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="4a33b-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="4a33b-113">IssuedTokenAuthentication</span></span>  

 <span data-ttu-id="4a33b-114">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="4a33b-114">Data type: string</span></span>  
  
 <span data-ttu-id="4a33b-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4a33b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a33b-116">Параметры проверки подлинности текущего выданного маркера для этой службы.</span><span class="sxs-lookup"><span data-stu-id="4a33b-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="4a33b-117">Одноранговый узел</span><span class="sxs-lookup"><span data-stu-id="4a33b-117">Peer</span></span>  

 <span data-ttu-id="4a33b-118">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="4a33b-118">Data type: string</span></span>  
  
 <span data-ttu-id="4a33b-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4a33b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a33b-120">Текущие параметры проверки подлинности учетных данных и подготовки для использования конечными точками однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="4a33b-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="4a33b-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="4a33b-121">SecureConversationAuthentication</span></span>  

 <span data-ttu-id="4a33b-122">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="4a33b-122">Data type: string</span></span>  
  
 <span data-ttu-id="4a33b-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4a33b-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a33b-124">Задает текущие параметры безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="4a33b-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="4a33b-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="4a33b-125">ServiceCertificate</span></span>  

 <span data-ttu-id="4a33b-126">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="4a33b-126">Data type: string</span></span>  
  
 <span data-ttu-id="4a33b-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4a33b-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a33b-128">Сертификат, связанный с этой службой.</span><span class="sxs-lookup"><span data-stu-id="4a33b-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="4a33b-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="4a33b-129">UserNameAuthentication</span></span>  

 <span data-ttu-id="4a33b-130">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="4a33b-130">Data type: string</span></span>  
  
 <span data-ttu-id="4a33b-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4a33b-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a33b-132">Параметры проверки имени пользователя и пароля для данной службы.</span><span class="sxs-lookup"><span data-stu-id="4a33b-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="4a33b-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="4a33b-133">WindowsAuthentication</span></span>  

 <span data-ttu-id="4a33b-134">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="4a33b-134">Data type: string</span></span>  
  
 <span data-ttu-id="4a33b-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4a33b-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a33b-136">Параметры проверки подлинности Windows для этой службы.</span><span class="sxs-lookup"><span data-stu-id="4a33b-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a33b-137">Требования</span><span class="sxs-lookup"><span data-stu-id="4a33b-137">Requirements</span></span>  
  
|<span data-ttu-id="4a33b-138">MOF</span><span class="sxs-lookup"><span data-stu-id="4a33b-138">MOF</span></span>|<span data-ttu-id="4a33b-139">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4a33b-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4a33b-140">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="4a33b-140">Namespace</span></span>|<span data-ttu-id="4a33b-141">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="4a33b-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a33b-142">См. также</span><span class="sxs-lookup"><span data-stu-id="4a33b-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceCredentials>
