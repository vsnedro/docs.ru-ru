---
title: Переименование службы WCF
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: 1179e7b235130e1967c79843b7a11f55622a01fb
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052056"
---
# <a name="renaming-a-wcf-service"></a><span data-ttu-id="a2740-102">Переименование службы WCF</span><span class="sxs-lookup"><span data-stu-id="a2740-102">Renaming a WCF Service</span></span>
<span data-ttu-id="a2740-103">В этом разделе описывается, как можно переименовать службу Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a2740-103">This topic describes how you can rename a Windows Communication Foundation (WCF) service.</span></span>  
  
## <a name="renaming-a-wcf-service"></a><span data-ttu-id="a2740-104">Переименование службы WCF</span><span class="sxs-lookup"><span data-stu-id="a2740-104">Renaming a WCF Service</span></span>  
 <span data-ttu-id="a2740-105">Чтобы переименовать службу в шаблоне Windows Communication Foundation (WCF), выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a2740-105">Perform the following steps to rename a service in a Windows Communication Foundation (WCF) template,</span></span>  
  
- <span data-ttu-id="a2740-106">Измените имя класса, реализующего службу.</span><span class="sxs-lookup"><span data-stu-id="a2740-106">Change the name of the class that implements the service.</span></span>  
  
- <span data-ttu-id="a2740-107">В файле конфигурации службы измените имя службы на новое выбранное имя, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a2740-107">In the configuration file of the service, change the name of the service to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="a2740-108">В зависимости от модели размещения файлом конфигурации может быть файл app.config или файл web.config.</span><span class="sxs-lookup"><span data-stu-id="a2740-108">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
- <span data-ttu-id="a2740-109">Если служба размещена на веб-узле, то она использует \* \* SVC\* -файл.</span><span class="sxs-lookup"><span data-stu-id="a2740-109">If your service is webhosted, it uses an *\*.svc* file.</span></span> <span data-ttu-id="a2740-110">Откройте SVC-файл и измените имя службы, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a2740-110">Open the svc file and modify the name of your service as indicated in the following example.</span></span> <span data-ttu-id="a2740-111">Этот шаг необязателен для резидентных приложений, так как у них нет SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="a2740-111">This step is not necessary for self-hosted applications, as there is no svc file.</span></span>  
  
```aspx-csharp
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a><span data-ttu-id="a2740-112">Переименование контракта службы WCF</span><span class="sxs-lookup"><span data-stu-id="a2740-112">Renaming a WCF Service Contract</span></span>  
  
- <span data-ttu-id="a2740-113">Выполните следующие действия для переименования контракта службы.</span><span class="sxs-lookup"><span data-stu-id="a2740-113">Perform the following steps to rename the service contract,</span></span>  
  
- <span data-ttu-id="a2740-114">Измените имя контракта службы.</span><span class="sxs-lookup"><span data-stu-id="a2740-114">Change the name of the service contract.</span></span>  
  
- <span data-ttu-id="a2740-115">В файле конфигурации службы измените имя контракта службы на новое выбранное имя, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a2740-115">In the configuration file of the service, change the name of the service contract to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="a2740-116">В зависимости от модели размещения файлом конфигурации может быть файл app.config или файл web.config.</span><span class="sxs-lookup"><span data-stu-id="a2740-116">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
