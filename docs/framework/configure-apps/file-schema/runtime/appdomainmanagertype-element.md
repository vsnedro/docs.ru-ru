---
title: Элемент <appDomainManagerType>
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: 8eb6129b3fafaeb81a94d5a4078e41a16583a226
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154434"
---
# <a name="appdomainmanagertype-element"></a><span data-ttu-id="c7ae6-102">Элемент \<appDomainManagerType></span><span class="sxs-lookup"><span data-stu-id="c7ae6-102">\<appDomainManagerType> Element</span></span>
<span data-ttu-id="c7ae6-103">Указывает тип, который служит диспетчером домена приложения для домена приложения, используемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c7ae6-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**  
  
## <a name="syntax"></a><span data-ttu-id="c7ae6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7ae6-104">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7ae6-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c7ae6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c7ae6-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c7ae6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7ae6-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c7ae6-107">Attributes</span></span>  
  
|<span data-ttu-id="c7ae6-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c7ae6-108">Attribute</span></span>|<span data-ttu-id="c7ae6-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c7ae6-109">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="c7ae6-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c7ae6-110">Required attribute.</span></span> <span data-ttu-id="c7ae6-111">Указывает имя типа, включая пространство имен, которое служит диспетчером доменов приложений для домена приложения по умолчанию в процессе.</span><span class="sxs-lookup"><span data-stu-id="c7ae6-111">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c7ae6-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c7ae6-112">Child Elements</span></span>  
 <span data-ttu-id="c7ae6-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c7ae6-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c7ae6-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c7ae6-114">Parent Elements</span></span>  
  
|<span data-ttu-id="c7ae6-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="c7ae6-115">Element</span></span>|<span data-ttu-id="c7ae6-116">Описание</span><span class="sxs-lookup"><span data-stu-id="c7ae6-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c7ae6-117">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c7ae6-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c7ae6-118">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="c7ae6-118">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7ae6-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="c7ae6-119">Remarks</span></span>  
 <span data-ttu-id="c7ae6-120">Чтобы указать тип диспетчера домена приложения, необходимо указать и этот элемент, и [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="c7ae6-120">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="c7ae6-121">Если один из этих элементов не указан, другой игнорируется.</span><span class="sxs-lookup"><span data-stu-id="c7ae6-121">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="c7ae6-122">При загрузке домена приложения по умолчанию создается <xref:System.TypeLoadException> исключение, если указанный тип не существует в сборке, заданной [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) элементом, и процесс не запускается.</span><span class="sxs-lookup"><span data-stu-id="c7ae6-122">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="c7ae6-123">При указании типа диспетчера домена приложения для домена приложения по умолчанию другие домены приложений, созданные из домена приложения по умолчанию, наследуют тип диспетчера домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c7ae6-123">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="c7ae6-124">Используйте <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> Свойства и, <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> чтобы указать другой тип диспетчера домена приложения для нового домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c7ae6-124">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="c7ae6-125">Чтобы указать тип диспетчера доменов приложений, приложение должно иметь полное доверие.</span><span class="sxs-lookup"><span data-stu-id="c7ae6-125">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="c7ae6-126">(Например, приложение, работающее на рабочем столе, имеет полное доверие.) Если приложение не имеет полного доверия, <xref:System.TypeLoadException> создается исключение.</span><span class="sxs-lookup"><span data-stu-id="c7ae6-126">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="c7ae6-127">Формат типа и пространства имен совпадает с форматом, используемым для <xref:System.Type.FullName%2A?displayProperty=nameWithType> Свойства.</span><span class="sxs-lookup"><span data-stu-id="c7ae6-127">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="c7ae6-128">Этот элемент конфигурации доступен только в .NET Framework 4 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="c7ae6-128">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7ae6-129">Пример</span><span class="sxs-lookup"><span data-stu-id="c7ae6-129">Example</span></span>  
 <span data-ttu-id="c7ae6-130">В следующем примере показано, как указать, что диспетчер домена приложения для домена приложения по умолчанию процесса — это `MyMgr` тип в `AdMgrExample` сборке.</span><span class="sxs-lookup"><span data-stu-id="c7ae6-130">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c7ae6-131">См. также</span><span class="sxs-lookup"><span data-stu-id="c7ae6-131">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c7ae6-132">\<appDomainManagerAssembly>Дерев</span><span class="sxs-lookup"><span data-stu-id="c7ae6-132">\<appDomainManagerAssembly> Element</span></span>](appdomainmanagerassembly-element.md)
- [<span data-ttu-id="c7ae6-133">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="c7ae6-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c7ae6-134">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="c7ae6-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c7ae6-135">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="c7ae6-135">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
