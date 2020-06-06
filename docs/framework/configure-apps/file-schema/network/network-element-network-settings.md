---
title: Элемент <network> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: f7cfcc3b9d5a717c23175cd15aa48ae97c828e57
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154820"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="40bf6-102">Элемент \<network> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="40bf6-102">\<network> Element (Network Settings)</span></span>
<span data-ttu-id="40bf6-103">Настраивает параметры сети для внешнего SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="40bf6-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<network>**

## <a name="syntax"></a><span data-ttu-id="40bf6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40bf6-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40bf6-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="40bf6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="40bf6-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="40bf6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40bf6-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="40bf6-107">Attributes</span></span>  
  
|<span data-ttu-id="40bf6-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="40bf6-108">Attribute</span></span>|<span data-ttu-id="40bf6-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="40bf6-109">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="40bf6-110">Указывает доменное имя клиента для использования в первоначальном запросе протокола SMTP для подключения к почтовому SMTP-серверу.</span><span class="sxs-lookup"><span data-stu-id="40bf6-110">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="40bf6-111">Значение по умолчанию — имя localhost локального компьютера, отправляющего запрос.</span><span class="sxs-lookup"><span data-stu-id="40bf6-111">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="40bf6-112">Указывает, следует ли использовать учетные данные пользователя по умолчанию для доступа к почтовому серверу SMTP для транзакций SMTP.</span><span class="sxs-lookup"><span data-stu-id="40bf6-112">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="40bf6-113">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="40bf6-113">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="40bf6-114">Указывает, используется ли протокол SSL для доступа к почтовому серверу SMTP.</span><span class="sxs-lookup"><span data-stu-id="40bf6-114">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="40bf6-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="40bf6-115">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="40bf6-116">Указывает имя узла почтового SMTP-сервера, используемого для транзакций SMTP.</span><span class="sxs-lookup"><span data-stu-id="40bf6-116">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="40bf6-117">Этот атрибут не имеет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="40bf6-117">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="40bf6-118">Указывает пароль, используемый для проверки подлинности на почтовом сервере SMTP.</span><span class="sxs-lookup"><span data-stu-id="40bf6-118">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="40bf6-119">Этот атрибут не имеет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="40bf6-119">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="40bf6-120">Указывает номер порта, используемый для подключения к почтовому SMTP-серверу.</span><span class="sxs-lookup"><span data-stu-id="40bf6-120">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="40bf6-121">По умолчанию используется значение 25.</span><span class="sxs-lookup"><span data-stu-id="40bf6-121">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="40bf6-122">Указывает имя поставщика услуг (SPN), используемое для проверки подлинности при использовании расширенной защиты для транзакций SMTP.</span><span class="sxs-lookup"><span data-stu-id="40bf6-122">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="40bf6-123">Этот атрибут не имеет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="40bf6-123">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="40bf6-124">Указывает имя пользователя, используемое для проверки подлинности на почтовом сервере SMTP.</span><span class="sxs-lookup"><span data-stu-id="40bf6-124">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="40bf6-125">Этот атрибут не имеет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="40bf6-125">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40bf6-126">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="40bf6-126">Child Elements</span></span>  
 <span data-ttu-id="40bf6-127">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="40bf6-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40bf6-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="40bf6-128">Parent Elements</span></span>  
  
|<span data-ttu-id="40bf6-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="40bf6-129">Element</span></span>|<span data-ttu-id="40bf6-130">Описание</span><span class="sxs-lookup"><span data-stu-id="40bf6-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40bf6-131">\<smtp>Элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="40bf6-131">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="40bf6-132">Настраивает параметры отправки почты по протоколу SMTP.</span><span class="sxs-lookup"><span data-stu-id="40bf6-132">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40bf6-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="40bf6-133">Remarks</span></span>  
 <span data-ttu-id="40bf6-134">Некоторые SMTP-серверы должны пройти проверку подлинности на сервере перед использованием.</span><span class="sxs-lookup"><span data-stu-id="40bf6-134">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="40bf6-135">Если вы хотите пройти проверку подлинности самостоятельно, используя сетевые учетные данные по умолчанию на узле, задайте `defaultCredentials` для атрибута значение `true` .</span><span class="sxs-lookup"><span data-stu-id="40bf6-135">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="40bf6-136"><xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType>Свойство можно использовать для получения текущего значения `defaultCredentials` атрибута из применимых файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="40bf6-136">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="40bf6-137">Для проверки подлинности на SMTP-сервере также можно использовать обычную проверку подлинности (имя пользователя и пароль).</span><span class="sxs-lookup"><span data-stu-id="40bf6-137">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="40bf6-138">Чтобы использовать этот параметр, необходимо указать допустимое имя пользователя и пароль для указанного SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="40bf6-138">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40bf6-139">Обычная проверка подлинности отправляет `userName` `password` значения и на сервер в незашифрованном виде.</span><span class="sxs-lookup"><span data-stu-id="40bf6-139">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="40bf6-140">Любой пользователь, отслеживающий сетевой трафик, может просматривать ваши учетные данные и использовать их для подключения к серверу.</span><span class="sxs-lookup"><span data-stu-id="40bf6-140">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="40bf6-141">Рекомендуется использовать более безопасный механизм проверки подлинности, например Kerberos или NT LAN Manager (NTLM). Если `defaultCredentials` имеет значение `true` , то используется протокол Kerberos или NTLM, если сервер поддерживает эти протоколы.</span><span class="sxs-lookup"><span data-stu-id="40bf6-141">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="40bf6-142">Параметры обычной проверки подлинности и сетевых учетных данных по умолчанию являются взаимоисключающими. Если задано `defaultCredentials` значение `true` и указано имя пользователя и пароль, используются учетные данные сети по умолчанию, а основные данные проверки подлинности игнорируются.</span><span class="sxs-lookup"><span data-stu-id="40bf6-142">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="40bf6-143">При обычной проверке подлинности при указании необходимо `userName` также указать `password` для проверки подлинности на почтовом сервере.</span><span class="sxs-lookup"><span data-stu-id="40bf6-143">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="40bf6-144"><xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType>Свойство можно использовать для получения текущего значения `userName` атрибута из применимых файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="40bf6-144">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="40bf6-145"><xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType>Свойство можно использовать для получения текущего значения `password` атрибута из применимых файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="40bf6-145">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="40bf6-146">`password`В целях безопасности атрибут обычно не указывается в файлах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="40bf6-146">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="40bf6-147">`clientDomain`Атрибут изменяет доменное имя клиента, используемое в первоначальном запросе протокола SMTP, на SMTP-сервер.</span><span class="sxs-lookup"><span data-stu-id="40bf6-147">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="40bf6-148">`clientDomain`Для атрибута можно задать полное доменное имя локального компьютера, а не имя localhost, используемое по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="40bf6-148">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="40bf6-149">Это обеспечивает более высокий уровень соответствия стандартам протокола SMTP.</span><span class="sxs-lookup"><span data-stu-id="40bf6-149">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="40bf6-150">Значение по умолчанию — имя localhost локального компьютера, отправляющего запрос.</span><span class="sxs-lookup"><span data-stu-id="40bf6-150">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="40bf6-151"><xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType>Свойство можно использовать для получения текущего значения `clientDomain` атрибута из применимых файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="40bf6-151">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="40bf6-152">`targetName`Атрибут используется для проверки подлинности при использовании расширенной защиты.</span><span class="sxs-lookup"><span data-stu-id="40bf6-152">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="40bf6-153">Значение по умолчанию — "SMTPSVC/", \<host> где \<host> — имя узла почтового SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="40bf6-153">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="40bf6-154"><xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType>Свойство можно использовать для получения текущего значения `targetName` атрибута из применимых файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="40bf6-154">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="40bf6-155">`enableSsl`Атрибут указывает, используется ли протокол SSL для доступа к почтовому серверу SMTP.</span><span class="sxs-lookup"><span data-stu-id="40bf6-155">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="40bf6-156"><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>Класс поддерживает только расширение службы SMTP для защиты SMTP по протоколу TLS, как определено в RFC 3207.</span><span class="sxs-lookup"><span data-stu-id="40bf6-156">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="40bf6-157">В этом режиме сеанс SMTP начинается на незашифрованном канале, после чего клиент отправляет на сервер команду STARTTLS, чтобы переключиться на безопасное взаимодействие с помощью SSL.</span><span class="sxs-lookup"><span data-stu-id="40bf6-157">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="40bf6-158">Дополнительные сведения см. в RFC 3207, опубликованных с помощью IETF.</span><span class="sxs-lookup"><span data-stu-id="40bf6-158">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="40bf6-159">Альтернативный способ подключения заключается в том, где сеанс SSL устанавливается перед отправкой любых команд протокола.</span><span class="sxs-lookup"><span data-stu-id="40bf6-159">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="40bf6-160">Этот метод подключения иногда называют SMTP и по умолчанию использует порт 465.</span><span class="sxs-lookup"><span data-stu-id="40bf6-160">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="40bf6-161">Этот альтернативный метод подключения, использующий SSL, в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="40bf6-161">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="40bf6-162"><xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType>Свойство можно использовать для получения текущего значения `enableSsl` атрибута из применимых файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="40bf6-162">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40bf6-163">Пример</span><span class="sxs-lookup"><span data-stu-id="40bf6-163">Example</span></span>  
 <span data-ttu-id="40bf6-164">В следующем примере задаются соответствующие параметры SMTP для отправки электронной почты с использованием сетевых учетных данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="40bf6-164">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="40bf6-165">См. также</span><span class="sxs-lookup"><span data-stu-id="40bf6-165">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="40bf6-166">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="40bf6-166">Network Settings Schema</span></span>](index.md)
