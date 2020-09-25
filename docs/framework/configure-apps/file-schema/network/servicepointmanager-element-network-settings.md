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
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="47161-103">Элемент \<servicePointManager> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="47161-103">\<servicePointManager> Element (Network Settings)</span></span>

<span data-ttu-id="47161-104">Настраивает подключения к сетевым ресурсам.</span><span class="sxs-lookup"><span data-stu-id="47161-104">Configures connections to network resources.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePointManager>**

## <a name="syntax"></a><span data-ttu-id="47161-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47161-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47161-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="47161-106">Attributes and Elements</span></span>  

 <span data-ttu-id="47161-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="47161-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47161-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="47161-108">Attributes</span></span>  
  
|<span data-ttu-id="47161-109">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="47161-109">**Attribute**</span></span>|<span data-ttu-id="47161-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="47161-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="47161-111">Указывает, должна ли система проверять имя сертификата на соответствие имени узла сервера перед использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="47161-111">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="47161-112">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="47161-112">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="47161-113">Указывает, должна ли система проверять, отозван ли сертификат перед использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="47161-113">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="47161-114">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="47161-114">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="47161-115">Указывает, как долго кэшируются разрешения службы доменных имен (DNS) в сочетании с параметром циклического перебора DNS в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="47161-115">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="47161-116">По умолчанию установлено значение 120 000 миллисекунд (2 минуты).</span><span class="sxs-lookup"><span data-stu-id="47161-116">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="47161-117">Указывает, должны ли разрешения DNS имен узлов с несколькими IP-адресами возвращать все адреса или только первый из них.</span><span class="sxs-lookup"><span data-stu-id="47161-117">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="47161-118">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="47161-118">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="47161-119">Указывает политику шифрования, применяемую к сеансу SSL/TLS в <xref:System.Net.ServicePointManager> экземпляре.</span><span class="sxs-lookup"><span data-stu-id="47161-119">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="47161-120">Возможные значения эквивалентны значениям <xref:System.Net.Security.EncryptionPolicy> перечисления.</span><span class="sxs-lookup"><span data-stu-id="47161-120">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="47161-121">Использование <xref:System.Security.Authentication.CipherAlgorithmType.Null> является обязательным, если для политики шифрования задано значение `NoEncryption` .</span><span class="sxs-lookup"><span data-stu-id="47161-121">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="47161-122">Значение по умолчанию — `RequireEncryption`.</span><span class="sxs-lookup"><span data-stu-id="47161-122">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="47161-123">Указывает, должны ли методы POST рассчитывать на получение `100-continue` ответа от сервера.</span><span class="sxs-lookup"><span data-stu-id="47161-123">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="47161-124">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="47161-124">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="47161-125">Указывает, используют ли подключения, управляемые диспетчером точек обслуживания, алгоритм Nagle.</span><span class="sxs-lookup"><span data-stu-id="47161-125">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="47161-126">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="47161-126">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47161-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="47161-127">Child Elements</span></span>  

 <span data-ttu-id="47161-128">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="47161-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="47161-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="47161-129">Parent Elements</span></span>  
  
|<span data-ttu-id="47161-130">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="47161-130">**Element**</span></span>|<span data-ttu-id="47161-131">**Описание**</span><span class="sxs-lookup"><span data-stu-id="47161-131">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="47161-132">Параметры</span><span class="sxs-lookup"><span data-stu-id="47161-132">Settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="47161-133">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="47161-133">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47161-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="47161-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="47161-135">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="47161-135">Configuration Files</span></span>  

 <span data-ttu-id="47161-136">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="47161-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47161-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="47161-137">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="47161-138">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="47161-138">Network Settings Schema</span></span>](index.md)
