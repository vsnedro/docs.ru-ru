---
title: Элемент <schemeSettings> (параметры URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 5a146b854239fd516125e66e05312e27b90c73ec
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91187021"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="9ddfb-102">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="9ddfb-102">\<schemeSettings> Element (Uri Settings)</span></span>

<span data-ttu-id="9ddfb-103">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="9ddfb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ddfb-104">Syntax</span></span>  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ddfb-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9ddfb-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9ddfb-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ddfb-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9ddfb-107">Attributes</span></span>  

 <span data-ttu-id="9ddfb-108">Нет</span><span class="sxs-lookup"><span data-stu-id="9ddfb-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9ddfb-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9ddfb-109">Child Elements</span></span>  
  
|<span data-ttu-id="9ddfb-110">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="9ddfb-110">**Element**</span></span>|<span data-ttu-id="9ddfb-111">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9ddfb-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9ddfb-112">add</span><span class="sxs-lookup"><span data-stu-id="9ddfb-112">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="9ddfb-113">Добавляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-113">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="9ddfb-114">пусто</span><span class="sxs-lookup"><span data-stu-id="9ddfb-114">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="9ddfb-115">Удаляет все существующие параметры схемы.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-115">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="9ddfb-116">remove</span><span class="sxs-lookup"><span data-stu-id="9ddfb-116">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="9ddfb-117">Удаляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-117">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ddfb-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9ddfb-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9ddfb-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="9ddfb-119">**Element**</span></span>|<span data-ttu-id="9ddfb-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9ddfb-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9ddfb-121">uri</span><span class="sxs-lookup"><span data-stu-id="9ddfb-121">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="9ddfb-122">Содержит параметры, определяющие, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="9ddfb-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ddfb-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="9ddfb-123">Remarks</span></span>  

 <span data-ttu-id="9ddfb-124">По умолчанию класс отменяет <xref:System.Uri?displayProperty=nameWithType> escape-символы в процентах, закодированные разделителями, перед выполнением сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-124">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="9ddfb-125">Это было реализовано в качестве механизма безопасности для атак, подобных следующим:</span><span class="sxs-lookup"><span data-stu-id="9ddfb-125">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="9ddfb-126">Если этот URI передается в модули, которые неправильно обрабатывают закодированные символы процента, это может привести к выполнению следующей команды на сервере:</span><span class="sxs-lookup"><span data-stu-id="9ddfb-126">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="9ddfb-127">По этой причине <xref:System.Uri?displayProperty=nameWithType> класс сначала отменяет escape-разделители путей, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-127">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="9ddfb-128">Результат передачи вредоносного URL-адреса выше в <xref:System.Uri?displayProperty=nameWithType> конструктор класса приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="9ddfb-128">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="9ddfb-129">Это поведение по умолчанию можно изменить, чтобы не отменять escape-символы в процентах с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-129">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9ddfb-130">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="9ddfb-130">Configuration Files</span></span>  

 <span data-ttu-id="9ddfb-131">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="9ddfb-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ddfb-132">Пример</span><span class="sxs-lookup"><span data-stu-id="9ddfb-132">Example</span></span>  

 <span data-ttu-id="9ddfb-133">В следующем примере показана конфигурация, используемая <xref:System.Uri> классом для поддержки неэкранированных разделителей пути в кодировке% для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="9ddfb-133">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="9ddfb-134">Сведения об элементе</span><span class="sxs-lookup"><span data-stu-id="9ddfb-134">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="9ddfb-135">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="9ddfb-135">Namespace</span></span>|<span data-ttu-id="9ddfb-136">Система</span><span class="sxs-lookup"><span data-stu-id="9ddfb-136">System</span></span>|  
|<span data-ttu-id="9ddfb-137">Имя схемы</span><span class="sxs-lookup"><span data-stu-id="9ddfb-137">Schema Name</span></span>||  
|<span data-ttu-id="9ddfb-138">Файл проверки</span><span class="sxs-lookup"><span data-stu-id="9ddfb-138">Validation File</span></span>||  
|<span data-ttu-id="9ddfb-139">Может быть пустым</span><span class="sxs-lookup"><span data-stu-id="9ddfb-139">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="9ddfb-140">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9ddfb-140">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="9ddfb-141">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="9ddfb-141">Network Settings Schema</span></span>](index.md)
