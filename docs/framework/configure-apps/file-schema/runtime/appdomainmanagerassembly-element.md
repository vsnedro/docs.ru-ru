---
title: Элемент <appDomainManagerAssembly>
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
ms.openlocfilehash: 4c4ea35bff17a0e5188f26884e93cf77173a7df8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154435"
---
# <a name="appdomainmanagerassembly-element"></a><span data-ttu-id="e9076-102">Элемент \<appDomainManagerAssembly></span><span class="sxs-lookup"><span data-stu-id="e9076-102">\<appDomainManagerAssembly> Element</span></span>
<span data-ttu-id="e9076-103">Указывает сборку, предоставляющую диспетчер домена приложения для домена приложения, по умолчанию используемого в процессе.</span><span class="sxs-lookup"><span data-stu-id="e9076-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerAssembly>**  
  
## <a name="syntax"></a><span data-ttu-id="e9076-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9076-104">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9076-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e9076-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e9076-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e9076-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9076-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e9076-107">Attributes</span></span>  
  
|<span data-ttu-id="e9076-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e9076-108">Attribute</span></span>|<span data-ttu-id="e9076-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e9076-109">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="e9076-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e9076-110">Required attribute.</span></span> <span data-ttu-id="e9076-111">Указывает отображаемое имя сборки, предоставляющей Диспетчер доменов приложений для домена приложения по умолчанию в процессе.</span><span class="sxs-lookup"><span data-stu-id="e9076-111">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9076-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e9076-112">Child Elements</span></span>  
 <span data-ttu-id="e9076-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e9076-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9076-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e9076-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e9076-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="e9076-115">Element</span></span>|<span data-ttu-id="e9076-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e9076-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e9076-117">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e9076-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e9076-118">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="e9076-118">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9076-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="e9076-119">Remarks</span></span>  
 <span data-ttu-id="e9076-120">Чтобы указать тип диспетчера домена приложения, необходимо указать и этот элемент, и [\<appDomainManagerType>](appdomainmanagertype-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="e9076-120">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="e9076-121">Если один из этих элементов не указан, другой игнорируется.</span><span class="sxs-lookup"><span data-stu-id="e9076-121">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="e9076-122">Когда загружается домен приложения по умолчанию, создается <xref:System.TypeLoadException> исключение, если указанная сборка не существует или сборка не содержит тип, указанный в элементе, [\<appDomainManagerType>](appdomainmanagertype-element.md) и процесс не запускается.</span><span class="sxs-lookup"><span data-stu-id="e9076-122">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="e9076-123">Если сборка найдена, но сведения о версии не совпадают, <xref:System.IO.FileLoadException> создается исключение.</span><span class="sxs-lookup"><span data-stu-id="e9076-123">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="e9076-124">При указании типа диспетчера домена приложения для домена приложения по умолчанию другие домены приложений, созданные из домена приложения по умолчанию, наследуют тип диспетчера домена приложения.</span><span class="sxs-lookup"><span data-stu-id="e9076-124">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="e9076-125">Используйте <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> Свойства и, <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> чтобы указать другой тип диспетчера домена приложения для нового домена приложения.</span><span class="sxs-lookup"><span data-stu-id="e9076-125">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="e9076-126">Чтобы указать тип диспетчера доменов приложений, приложение должно иметь полное доверие.</span><span class="sxs-lookup"><span data-stu-id="e9076-126">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="e9076-127">(Например, приложение, работающее на рабочем столе, имеет полное доверие.) Если приложение не имеет полного доверия, <xref:System.TypeLoadException> создается исключение.</span><span class="sxs-lookup"><span data-stu-id="e9076-127">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="e9076-128">Сведения о формате отображаемого имени сборки см. в описании <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> Свойства.</span><span class="sxs-lookup"><span data-stu-id="e9076-128">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="e9076-129">Этот элемент конфигурации доступен только в .NET Framework 4 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="e9076-129">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9076-130">Пример</span><span class="sxs-lookup"><span data-stu-id="e9076-130">Example</span></span>  
 <span data-ttu-id="e9076-131">В следующем примере показано, как указать, что диспетчер домена приложения для домена приложения по умолчанию процесса — это `MyMgr` тип в `AdMgrExample` сборке.</span><span class="sxs-lookup"><span data-stu-id="e9076-131">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9076-132">См. также</span><span class="sxs-lookup"><span data-stu-id="e9076-132">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e9076-133">\<appDomainManagerType>Дерев</span><span class="sxs-lookup"><span data-stu-id="e9076-133">\<appDomainManagerType> Element</span></span>](appdomainmanagertype-element.md)
- [<span data-ttu-id="e9076-134">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="e9076-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e9076-135">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e9076-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e9076-136">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="e9076-136">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
