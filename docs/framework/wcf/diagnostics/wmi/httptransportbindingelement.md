---
description: 'Дополнительные сведения о: HttpTransportBindingElement'
title: HttpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
ms.openlocfilehash: 6c516dd7124d52828145787d55421d12031c2d36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757375"
---
# <a name="httptransportbindingelement"></a>HttpTransportBindingElement

HttpTransportBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс HttpTransportBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс HttpTransportBindingElement имеет следующие свойства.  
  
### <a name="allowcookies"></a>AllowCookies  

 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Значение, определяющее, принимает ли клиент файлы Cookie и распространяет ли он их на будущие запросы.  
  
### <a name="authenticationscheme"></a>AuthenticationScheme  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Схема проверки подлинности, используемая для проверки подлинности клиентских запросов, обрабатываемых HTTP-прослушивателем.  
  
### <a name="bypassproxyonlocal"></a>BypassProxyOnLocal  

 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее, игнорируются ли прокси-серверы для локальных адресов.  
  
### <a name="hostnamecomparisonmode"></a>HostNameComparisonMode  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее, используется ли имя узла для доступа к службе при сопоставлении по универсальному коду ресурса (URI).  
  
### <a name="keepaliveenabled"></a>KeepAliveEnabled  

 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Когда включено, соединения HTTP остаются в активном состоянии независимо от уровня активности.  
  
### <a name="maxbuffersize"></a>MaxBufferSize  

 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальный размер буферного пула.  
  
### <a name="proxyaddress"></a>ProxyAddress  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Универсальный код ресурса (URI), который содержит адрес прокси-сервера, используемого для выполнения HTTP-запросов.  
  
### <a name="proxyauthenticationscheme"></a>ProxyAuthenticationScheme  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Схема проверки подлинности, используемая для проверки подлинности клиентских запросов, обрабатываемых прокси-сервером HTTP.  
  
### <a name="realm"></a>Realm  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Область проверки подлинности.  
  
### <a name="transfermode"></a>TransferMode  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее статус сообщения: помещено в буфер или поток, запрос или ответ.  
  
### <a name="unsafeconnectionntlmauthentication"></a>UnsafeConnectionNtlmAuthentication  

 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее, разрешено ли на сервере совместное использование небезопасных подключений.  
  
### <a name="usedefaultwebproxy"></a>UseDefaultWebProxy  

 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее, используются ли параметры прокси-сервера компьютера или пользователя.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
