---
title: Элемент <servicePointManager> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: b7333016fea2d46285d3c98181c0ca4904c376f8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089128"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="74dd2-102">Элемент \<servicePointManager> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="74dd2-102">\<servicePointManager> Element (Network Settings)</span></span>
<span data-ttu-id="74dd2-103">Настраивает подключения к сетевым ресурсам.</span><span class="sxs-lookup"><span data-stu-id="74dd2-103">Configures connections to network resources.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePointManager>**

## <a name="syntax"></a><span data-ttu-id="74dd2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74dd2-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74dd2-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="74dd2-105">Attributes and Elements</span></span>  
 <span data-ttu-id="74dd2-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="74dd2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74dd2-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="74dd2-107">Attributes</span></span>  
  
|<span data-ttu-id="74dd2-108">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="74dd2-108">**Attribute**</span></span>|<span data-ttu-id="74dd2-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="74dd2-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="74dd2-110">Указывает, должна ли система проверять имя сертификата на соответствие имени узла сервера перед использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="74dd2-110">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="74dd2-111">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="74dd2-111">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="74dd2-112">Указывает, должна ли система проверять, отозван ли сертификат перед использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="74dd2-112">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="74dd2-113">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="74dd2-113">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="74dd2-114">Указывает, как долго кэшируются разрешения службы доменных имен (DNS) в сочетании с параметром циклического перебора DNS в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="74dd2-114">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="74dd2-115">По умолчанию установлено значение 120 000 миллисекунд (2 минуты).</span><span class="sxs-lookup"><span data-stu-id="74dd2-115">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="74dd2-116">Указывает, должны ли разрешения DNS имен узлов с несколькими IP-адресами возвращать все адреса или только первый из них.</span><span class="sxs-lookup"><span data-stu-id="74dd2-116">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="74dd2-117">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="74dd2-117">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="74dd2-118">Указывает политику шифрования, применяемую к сеансу SSL/TLS в <xref:System.Net.ServicePointManager> экземпляре.</span><span class="sxs-lookup"><span data-stu-id="74dd2-118">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="74dd2-119">Возможные значения эквивалентны значениям <xref:System.Net.Security.EncryptionPolicy> перечисления.</span><span class="sxs-lookup"><span data-stu-id="74dd2-119">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="74dd2-120">Использование <xref:System.Security.Authentication.CipherAlgorithmType.Null> является обязательным, если для политики шифрования задано значение `NoEncryption` .</span><span class="sxs-lookup"><span data-stu-id="74dd2-120">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="74dd2-121">Значение по умолчанию — `RequireEncryption`.</span><span class="sxs-lookup"><span data-stu-id="74dd2-121">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="74dd2-122">Указывает, должны ли методы POST рассчитывать на получение `100-continue` ответа от сервера.</span><span class="sxs-lookup"><span data-stu-id="74dd2-122">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="74dd2-123">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="74dd2-123">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="74dd2-124">Указывает, используют ли подключения, управляемые диспетчером точек обслуживания, алгоритм Nagle.</span><span class="sxs-lookup"><span data-stu-id="74dd2-124">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="74dd2-125">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="74dd2-125">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74dd2-126">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="74dd2-126">Child Elements</span></span>  
 <span data-ttu-id="74dd2-127">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="74dd2-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74dd2-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="74dd2-128">Parent Elements</span></span>  
  
|<span data-ttu-id="74dd2-129">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="74dd2-129">**Element**</span></span>|<span data-ttu-id="74dd2-130">**Описание**</span><span class="sxs-lookup"><span data-stu-id="74dd2-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="74dd2-131">Параметры</span><span class="sxs-lookup"><span data-stu-id="74dd2-131">Settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="74dd2-132">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="74dd2-132">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74dd2-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="74dd2-133">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="74dd2-134">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="74dd2-134">Configuration Files</span></span>  
 <span data-ttu-id="74dd2-135">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="74dd2-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74dd2-136">См. также</span><span class="sxs-lookup"><span data-stu-id="74dd2-136">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="74dd2-137">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="74dd2-137">Network Settings Schema</span></span>](index.md)
