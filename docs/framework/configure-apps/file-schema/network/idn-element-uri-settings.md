---
title: Элемент <idn> (параметры URI)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: f45922ecd5f7476362aab5348d91415d8e31c53f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195406"
---
# <a name="idn-element-uri-settings"></a><span data-ttu-id="3bd05-102">Элемент \<idn> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="3bd05-102">\<idn> Element (Uri Settings)</span></span>

<span data-ttu-id="3bd05-103">Указывает, применяется ли синтаксический анализ международного доменного имени (IDN) к доменному имени.</span><span class="sxs-lookup"><span data-stu-id="3bd05-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<idn>**  
  
## <a name="syntax"></a><span data-ttu-id="3bd05-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3bd05-104">Syntax</span></span>  
  
```xml
<idn
  enabled="All|AllExceptIntranet|None"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3bd05-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3bd05-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3bd05-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3bd05-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3bd05-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3bd05-107">Attributes</span></span>  

|<span data-ttu-id="3bd05-108">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="3bd05-108">**Element**</span></span>|<span data-ttu-id="3bd05-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3bd05-109">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="3bd05-110">Указывает, применяется ли синтаксический анализ международного доменного имени (IDN) к доменному имени. значение по умолчанию — None.</span><span class="sxs-lookup"><span data-stu-id="3bd05-110">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  

### <a name="child-elements"></a><span data-ttu-id="3bd05-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3bd05-111">Child elements</span></span>

<span data-ttu-id="3bd05-112">Нет</span><span class="sxs-lookup"><span data-stu-id="3bd05-112">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="3bd05-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3bd05-113">Parent elements</span></span>

|<span data-ttu-id="3bd05-114">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="3bd05-114">**Element**</span></span>|<span data-ttu-id="3bd05-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3bd05-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3bd05-116">uri</span><span class="sxs-lookup"><span data-stu-id="3bd05-116">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="3bd05-117">Содержит параметры, определяющие, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="3bd05-117">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  

## <a name="remarks"></a><span data-ttu-id="3bd05-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="3bd05-118">Remarks</span></span>

<span data-ttu-id="3bd05-119">Существующий <xref:System.Uri> класс был расширен в .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="3bd05-119">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="3bd05-120">3,0 с пакетом обновления 1 (SP1) и 2,0 с пакетом обновления 1 (SP1) с поддержкой международных идентификаторов ресурсов (IRI) и международных доменных имен (IDN).</span><span class="sxs-lookup"><span data-stu-id="3bd05-120">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="3bd05-121">Текущие пользователи не увидят каких бы то ни было изменений в работе .NET Framework 2,0, если они специально не включают поддержку IRI и IDN.</span><span class="sxs-lookup"><span data-stu-id="3bd05-121">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="3bd05-122">Это обеспечивает совместимость приложений с предыдущими версиями платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3bd05-122">This ensures application compatibility with prior versions of the .NET Framework.</span></span>

<span data-ttu-id="3bd05-123">Чтобы включить поддержку IRI, требуются следующие два изменения:</span><span class="sxs-lookup"><span data-stu-id="3bd05-123">To enable support for IRI, the following two changes are required:</span></span>

1. <span data-ttu-id="3bd05-124">Добавьте следующую строку в файл machine.config в каталоге .NET Framework 2,0:</span><span class="sxs-lookup"><span data-stu-id="3bd05-124">Add the following line to the machine.config file under the .NET Framework 2.0 directory:</span></span>
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="3bd05-125">Укажите, следует ли применять синтаксический анализ международного доменного имени (IDN) к доменному имени и следует ли применять правила синтаксического анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="3bd05-125">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="3bd05-126">Это можно сделать в файле machine.config или в файле app.config.</span><span class="sxs-lookup"><span data-stu-id="3bd05-126">This can be done in the machine.config or in the app.config file.</span></span>

 <span data-ttu-id="3bd05-127">Существует три возможных значения для IDN в зависимости от используемых DNS-серверов.</span><span class="sxs-lookup"><span data-stu-id="3bd05-127">There are three possible values for IDN depending on the DNS servers that are used:</span></span>

- <span data-ttu-id="3bd05-128">IDN включен = ALL</span><span class="sxs-lookup"><span data-stu-id="3bd05-128">idn enabled = All</span></span>  

     <span data-ttu-id="3bd05-129">При этом значении имена доменов из Юникода будут преобразовываться в их эквиваленты в Punycode (IDN-имена).</span><span class="sxs-lookup"><span data-stu-id="3bd05-129">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>

- <span data-ttu-id="3bd05-130">IDN включен = Аллексцептинтранет</span><span class="sxs-lookup"><span data-stu-id="3bd05-130">idn enabled = AllExceptIntranet</span></span>

     <span data-ttu-id="3bd05-131">Это значение преобразует все доменные имена Юникода, которые не находятся в локальной интрасети, для использования эквивалентов в Punycode (IDN-имен).</span><span class="sxs-lookup"><span data-stu-id="3bd05-131">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="3bd05-132">В этом случае для обработки международных имен в локальной интрасети DNS-серверы, используемые для интрасети, должны поддерживать разрешение имен Юникода.</span><span class="sxs-lookup"><span data-stu-id="3bd05-132">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>

- <span data-ttu-id="3bd05-133">IDN включен = None</span><span class="sxs-lookup"><span data-stu-id="3bd05-133">idn enabled = None</span></span>

     <span data-ttu-id="3bd05-134">При этом значении имена доменов в Юникоде не будут преобразовываться в их эквиваленты в Punycode.</span><span class="sxs-lookup"><span data-stu-id="3bd05-134">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="3bd05-135">Это значение по умолчанию, которое совместимо с поведением платформы .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="3bd05-135">This is the default value which is consistent with the .NET Framework 2.0 behavior.</span></span>

 <span data-ttu-id="3bd05-136">При включенном IDN метки в Юникоде в доменном имени будут преобразованы в аналоги в кодировке Punicode.</span><span class="sxs-lookup"><span data-stu-id="3bd05-136">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="3bd05-137">Имена Punicode содержат только символы ASCII и всегда начинаются с префикса "xn--".</span><span class="sxs-lookup"><span data-stu-id="3bd05-137">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="3bd05-138">Это сделано для того, чтобы поддерживать существующие DNS-серверы в интрасети, так как большинство DNS-серверов поддерживает только символы ASCII (см. RFC 3940).</span><span class="sxs-lookup"><span data-stu-id="3bd05-138">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>

### <a name="configuration-files"></a><span data-ttu-id="3bd05-139">Файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3bd05-139">Configuration files</span></span>

<span data-ttu-id="3bd05-140">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="3bd05-140">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="3bd05-141">Пример</span><span class="sxs-lookup"><span data-stu-id="3bd05-141">Example</span></span>

<span data-ttu-id="3bd05-142">В следующем примере показана конфигурация, используемая <xref:System.Uri> классом для поддержки синтаксического анализа IRI и имен IDN:</span><span class="sxs-lookup"><span data-stu-id="3bd05-142">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names:</span></span>

```xml
<configuration>
  <uri>
    <idn enabled="All" />
    <iriParsing enabled="true" />
  </uri>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="3bd05-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3bd05-143">See also</span></span>

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="3bd05-144">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="3bd05-144">Network Settings Schema</span></span>](index.md)
