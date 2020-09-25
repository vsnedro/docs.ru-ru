---
title: Элемент <servicePointManager> (параметры сети)
description: <servicePointManager>Элемент Параметры сети настраивает подключения к параметрам сетевых ресурсов в .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: a6678a8fe7c6f962529f9d946b103b6224d58602
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174112"
---
# <a name="servicepointmanager-element-network-settings"></a>Элемент \<servicePointManager> (параметры сети)

Настраивает подключения к сетевым ресурсам.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePointManager>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Attribute**|**Описание**|  
|-------------------|---------------------|  
|`checkCertificateName`|Указывает, должна ли система проверять имя сертификата на соответствие имени узла сервера перед использованием сертификата. Значение по умолчанию — `true`.|  
|`checkCertificateRevocationList`|Указывает, должна ли система проверять, отозван ли сертификат перед использованием сертификата. Значение по умолчанию — `false`.|  
|`dnsRefreshTimeout`|Указывает, как долго кэшируются разрешения службы доменных имен (DNS) в сочетании с параметром циклического перебора DNS в миллисекундах. По умолчанию установлено значение 120 000 миллисекунд (2 минуты).|  
|`enableDnsRoundRobin`|Указывает, должны ли разрешения DNS имен узлов с несколькими IP-адресами возвращать все адреса или только первый из них. Значение по умолчанию — `false`.|  
|`encryptionPolicy`|Указывает политику шифрования, применяемую к сеансу SSL/TLS в <xref:System.Net.ServicePointManager> экземпляре. Возможные значения эквивалентны значениям <xref:System.Net.Security.EncryptionPolicy> перечисления. Использование <xref:System.Security.Authentication.CipherAlgorithmType.Null> является обязательным, если для политики шифрования задано значение `NoEncryption` . Значение по умолчанию — `RequireEncryption`.|  
|`expect100Continue`|Указывает, должны ли методы POST рассчитывать на получение `100-continue` ответа от сервера. Значение по умолчанию — `true`.|  
|`useNagleAlgorithm`|Указывает, используют ли подключения, управляемые диспетчером точек обслуживания, алгоритм Nagle. Значение по умолчанию — `true`.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[Параметры](settings-element-network-settings.md)|Настраивает основные параметры сети для пространства имен <xref:System.Net>.|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="configuration-files"></a>Файлы конфигурации  

 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [Схема параметров сети](index.md)
