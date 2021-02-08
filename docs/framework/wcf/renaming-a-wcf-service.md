---
description: 'Дополнительные сведения: переименование службы WCF'
title: Переименование службы WCF
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: 8d75e43f4bda97e8ee6de34b039eb1236d6c4a6d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779170"
---
# <a name="renaming-a-wcf-service"></a>Переименование службы WCF

В этом разделе описывается, как можно переименовать службу Windows Communication Foundation (WCF).  
  
## <a name="renaming-a-wcf-service"></a>Переименование службы WCF  

 Чтобы переименовать службу в шаблоне Windows Communication Foundation (WCF), выполните следующие действия.  
  
- Измените имя класса, реализующего службу.  
  
- В файле конфигурации службы измените имя службы на новое выбранное имя, как показано в следующем примере. В зависимости от модели размещения файлом конфигурации может быть файл app.config или файл web.config.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
- Если служба размещена на веб-узле, то она использует *\* SVC* -файл. Откройте SVC-файл и измените имя службы, как показано в следующем примере. Этот шаг необязателен для резидентных приложений, так как у них нет SVC-файла.  
  
```aspx-csharp
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a>Переименование контракта службы WCF  
  
- Выполните следующие действия для переименования контракта службы.  
  
- Измените имя контракта службы.  
  
- В файле конфигурации службы измените имя контракта службы на новое выбранное имя, как показано в следующем примере. В зависимости от модели размещения файлом конфигурации может быть файл app.config или файл web.config.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
