---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: c63e1b3de464b306f46e2f0935b1208d7262925a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274196"
---
# <a name="clientcredentials"></a>ClientCredentials

ClientCredentials  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс ClientCredentials не определяет никакие методы.  
  
## <a name="properties"></a>Свойства  

 Класс ClientCredentials имеет следующие свойства.  
  
### <a name="clientcertificate"></a>ClientCertificate  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Сертификат X.509, используемый клиентом для проверки подлинности службы.  
  
### <a name="httpdigest"></a>HttpDigest  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Текущие учетные данные хэш-кода HTTP.  
  
### <a name="issuedtoken"></a>IssuedToken  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Адрес конечной точки и привязка, используемые для связи с локальной службой маркеров безопасности.  
  
### <a name="peer"></a>Одноранговый узел  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Учетные данные, используемые одноранговым узлом для подтверждения своей подлинности при подключении к другим узлам в сетке.  
  
### <a name="servicecertificate"></a>ServiceCertificate  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Сертификат X.509 службы.  
  
### <a name="supportinteractive"></a>SupportInteractive  

 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, определяющее, поддерживают ли учетные данные интерактивное согласование.  
  
### <a name="username"></a>UserName  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Имя пользователя и пароль, используемые клиентом для подтверждения своей подлинности при подключении к службе.  
  
### <a name="windows"></a>Windows  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Учетные данные Windows, используемые клиентом для подтверждения своей подлинности при подключении к службе.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Description.ClientCredentials>
