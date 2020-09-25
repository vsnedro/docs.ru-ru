---
title: Элемент <network> (параметры сети)
description: <network>Элемент Параметры сети настраивает параметры сети для параметров внешнего SMTP-сервера в .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: cd142febc0b3aacf1be7978178a6a05d9b9aebbf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190284"
---
# <a name="network-element-network-settings"></a>Элемент \<network> (параметры сети)

Настраивает параметры сети для внешнего SMTP-сервера.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<network>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<network  
  clientDomain="string"
  defaultCredentials="true|false"  
  enableSsl="true|false"  
  host="string"
  password="string"  
  port="integer"
  targetName="string"  
  userName="string"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`clientDomain`|Указывает доменное имя клиента для использования в первоначальном запросе протокола SMTP для подключения к почтовому SMTP-серверу. Значение по умолчанию — имя localhost локального компьютера, отправляющего запрос.|  
|`defaultCredentials`|Указывает, следует ли использовать учетные данные пользователя по умолчанию для доступа к почтовому серверу SMTP для транзакций SMTP. Значение по умолчанию — `false`.|  
|`enableSsl`|Указывает, используется ли протокол SSL для доступа к почтовому серверу SMTP. Значение по умолчанию — `false`.|  
|`host`|Указывает имя узла почтового SMTP-сервера, используемого для транзакций SMTP. Этот атрибут не имеет значения по умолчанию.|  
|`password`|Указывает пароль, используемый для проверки подлинности на почтовом сервере SMTP. Этот атрибут не имеет значения по умолчанию.|  
|`port`|Указывает номер порта, используемый для подключения к почтовому SMTP-серверу. По умолчанию используется значение 25.|  
|`targetName`|Указывает имя поставщика услуг (SPN), используемое для проверки подлинности при использовании расширенной защиты для транзакций SMTP. Этот атрибут не имеет значения по умолчанию.|  
|`userName`|Указывает имя пользователя, используемое для проверки подлинности на почтовом сервере SMTP. Этот атрибут не имеет значения по умолчанию.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[Элемент \<smtp> (параметры сети)](smtp-element-network-settings.md)|Настраивает параметры отправки почты по протоколу SMTP.|  
  
## <a name="remarks"></a>Remarks  

 Некоторые SMTP-серверы должны пройти проверку подлинности на сервере перед использованием. Если вы хотите пройти проверку подлинности самостоятельно, используя сетевые учетные данные по умолчанию на узле, задайте `defaultCredentials` для атрибута значение `true` . <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType>Свойство можно использовать для получения текущего значения `defaultCredentials` атрибута из применимых файлов конфигурации.  
  
 Для проверки подлинности на SMTP-сервере также можно использовать обычную проверку подлинности (имя пользователя и пароль). Чтобы использовать этот параметр, необходимо указать допустимое имя пользователя и пароль для указанного SMTP-сервера.  
  
> [!NOTE]
> Обычная проверка подлинности отправляет `userName` `password` значения и на сервер в незашифрованном виде. Любой пользователь, отслеживающий сетевой трафик, может просматривать ваши учетные данные и использовать их для подключения к серверу. Рекомендуется использовать более безопасный механизм проверки подлинности, например Kerberos или NT LAN Manager (NTLM). Если `defaultCredentials` имеет значение `true` , то используется протокол Kerberos или NTLM, если сервер поддерживает эти протоколы.  
  
 Параметры обычной проверки подлинности и сетевых учетных данных по умолчанию являются взаимоисключающими. Если задано `defaultCredentials` значение `true` и указано имя пользователя и пароль, используются учетные данные сети по умолчанию, а основные данные проверки подлинности игнорируются.  
  
 При обычной проверке подлинности при указании необходимо `userName` также указать `password` для проверки подлинности на почтовом сервере.  
  
 <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType>Свойство можно использовать для получения текущего значения `userName` атрибута из применимых файлов конфигурации. <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType>Свойство можно использовать для получения текущего значения `password` атрибута из применимых файлов конфигурации. `password`В целях безопасности атрибут обычно не указывается в файлах конфигурации.  
  
 `clientDomain`Атрибут изменяет доменное имя клиента, используемое в первоначальном запросе протокола SMTP, на SMTP-сервер. `clientDomain`Для атрибута можно задать полное доменное имя локального компьютера, а не имя localhost, используемое по умолчанию. Это обеспечивает более высокий уровень соответствия стандартам протокола SMTP. Значение по умолчанию — имя localhost локального компьютера, отправляющего запрос. <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType>Свойство можно использовать для получения текущего значения `clientDomain` атрибута из применимых файлов конфигурации.  
  
 `targetName`Атрибут используется для проверки подлинности при использовании расширенной защиты. Значение по умолчанию — "SMTPSVC/", \<host> где \<host> — имя узла почтового SMTP-сервера. <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType>Свойство можно использовать для получения текущего значения `targetName` атрибута из применимых файлов конфигурации.  
  
 `enableSsl`Атрибут указывает, используется ли протокол SSL для доступа к почтовому серверу SMTP. <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>Класс поддерживает только расширение службы SMTP для защиты SMTP по протоколу TLS, как определено в RFC 3207. В этом режиме сеанс SMTP начинается на незашифрованном канале, после чего клиент отправляет на сервер команду STARTTLS, чтобы переключиться на безопасное взаимодействие с помощью SSL. Дополнительные сведения см. в RFC 3207, опубликованных с помощью IETF.  
  
 Альтернативный способ подключения заключается в том, где сеанс SSL устанавливается перед отправкой любых команд протокола. Этот метод подключения иногда называют SMTP и по умолчанию использует порт 465. Этот альтернативный метод подключения, использующий SSL, в настоящее время не поддерживается.  
  
 <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType>Свойство можно использовать для получения текущего значения `enableSsl` атрибута из применимых файлов конфигурации.  
  
## <a name="example"></a>Пример  

 В следующем примере задаются соответствующие параметры SMTP для отправки электронной почты с использованием сетевых учетных данных по умолчанию.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
        <network  
          clientDomain="www.contoso.com"  
          defaultCredentials="true"  
          enableSsl="false"  
          host="mail.contoso.com"  
          port="25"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [Схема параметров сети](index.md)
