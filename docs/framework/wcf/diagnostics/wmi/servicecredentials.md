---
description: 'Дополнительные сведения о: ServiceCredentials'
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: bfd025a8f671a3c5aea537059cde0e751cfa9bb9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715552"
---
# <a name="servicecredentials"></a>ServiceCredentials

ServiceCredentials  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
## <a name="methods"></a>Методы  

 Класс ServiceCredentials не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс ServiceCredentials имеет следующие свойства.  
  
### <a name="clientcertificate"></a>ClientCertificate  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Параметры проверки подлинности сертификата клиента и подготовки для этой службы.  
  
### <a name="issuedtokenauthentication"></a>IssuedTokenAuthentication  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Параметры проверки подлинности текущего выданного маркера для этой службы.  
  
### <a name="peer"></a>Одноранговый узел  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Текущие параметры проверки подлинности учетных данных и подготовки для использования конечными точками однорангового транспорта.  
  
### <a name="secureconversationauthentication"></a>SecureConversationAuthentication  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Задает текущие параметры безопасного обмена данными.  
  
### <a name="servicecertificate"></a>ServiceCertificate  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Сертификат, связанный с этой службой.  
  
### <a name="usernameauthentication"></a>UserNameAuthentication  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Параметры проверки имени пользователя и пароля для данной службы.  
  
### <a name="windowsauthentication"></a>WindowsAuthentication  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Параметры проверки подлинности Windows для этой службы.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Description.ServiceCredentials>
