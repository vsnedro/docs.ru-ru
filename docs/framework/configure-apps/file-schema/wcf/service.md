---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: dcc32f5aa055942408a3f01d37b5aa27ac0f51ee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173774"
---
# \<service>

<span data-ttu-id="f21b5-101">Элемент `service` содержит параметры для службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f21b5-101">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="f21b5-102">Он также содержит конечные точки, предоставляющие доступ к службе.</span><span class="sxs-lookup"><span data-stu-id="f21b5-102">It also contains endpoints that expose the service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<service>**  
  
## <a name="syntax"></a><span data-ttu-id="f21b5-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f21b5-103">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f21b5-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f21b5-104">Attributes and Elements</span></span>  

 <span data-ttu-id="f21b5-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f21b5-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f21b5-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f21b5-106">Attributes</span></span>  
  
|<span data-ttu-id="f21b5-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f21b5-107">Attribute</span></span>|<span data-ttu-id="f21b5-108">Описание</span><span class="sxs-lookup"><span data-stu-id="f21b5-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f21b5-109">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="f21b5-109">behaviorConfiguration</span></span>|<span data-ttu-id="f21b5-110">Строка, содержащая имя поведения, которое следует использовать для создания экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="f21b5-110">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="f21b5-111">Имя поведения должно входить в область действия в точке определения службы.</span><span class="sxs-lookup"><span data-stu-id="f21b5-111">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="f21b5-112">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="f21b5-112">The default value is an empty string.</span></span>|  
|<span data-ttu-id="f21b5-113">name</span><span class="sxs-lookup"><span data-stu-id="f21b5-113">name</span></span>|<span data-ttu-id="f21b5-114">Требуемый строковый атрибут, указывающий тип службы, экземпляр которой создается.</span><span class="sxs-lookup"><span data-stu-id="f21b5-114">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="f21b5-115">Этот параметр должен иметь значение допустимого типа.</span><span class="sxs-lookup"><span data-stu-id="f21b5-115">This setting must equate to a valid type.</span></span> <span data-ttu-id="f21b5-116">Формат должен быть `Namespace.Class.`.</span><span class="sxs-lookup"><span data-stu-id="f21b5-116">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f21b5-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f21b5-117">Child Elements</span></span>  
  
|<span data-ttu-id="f21b5-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="f21b5-118">Element</span></span>|<span data-ttu-id="f21b5-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f21b5-119">Description</span></span>|  
|-------------|-----------------|  
|[\<endpoint>](endpoint-element.md)|<span data-ttu-id="f21b5-120">Коллекция элементов `endpoint`, которые обеспечивают доступ к данной службе.</span><span class="sxs-lookup"><span data-stu-id="f21b5-120">A collection of `endpoint` elements that expose this service.</span></span>|  
|[\<host>](host.md)|<span data-ttu-id="f21b5-121">Задает узел данного экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="f21b5-121">Specifies the host of this service instance.</span></span> <span data-ttu-id="f21b5-122">Это элемент типа <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="f21b5-122">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f21b5-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f21b5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f21b5-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="f21b5-124">Element</span></span>|<span data-ttu-id="f21b5-125">Описание</span><span class="sxs-lookup"><span data-stu-id="f21b5-125">Description</span></span>|  
|-------------|-----------------|  
|[\<services>](services.md)|<span data-ttu-id="f21b5-126">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="f21b5-126">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f21b5-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="f21b5-127">Remarks</span></span>  

 <span data-ttu-id="f21b5-128">Службы задаются в разделе `services` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f21b5-128">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="f21b5-129">Сборка может содержать любое число служб.</span><span class="sxs-lookup"><span data-stu-id="f21b5-129">An assembly can contain any number of services.</span></span> <span data-ttu-id="f21b5-130">Для каждой службы используется собственный раздел конфигурации `service`.</span><span class="sxs-lookup"><span data-stu-id="f21b5-130">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="f21b5-131">В этом разделе определяются контракт, поведение и конечные точки конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="f21b5-131">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="f21b5-132">Элемент `behaviorConfiguration` также является необязательным.</span><span class="sxs-lookup"><span data-stu-id="f21b5-132">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="f21b5-133">Он указывает поведение, используемое службой.</span><span class="sxs-lookup"><span data-stu-id="f21b5-133">It identifies the behavior the service uses.</span></span> <span data-ttu-id="f21b5-134">Поведение, заданное в данном атрибуте, должно быть связано с поведением в области в том же файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f21b5-134">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="f21b5-135">Каждая служба предоставляет доступ к одной или нескольким конечным точкам, которые имеют собственные адреса и привязки.</span><span class="sxs-lookup"><span data-stu-id="f21b5-135">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="f21b5-136">Все привязки в файле конфигурации должны быть определены в области файла.</span><span class="sxs-lookup"><span data-stu-id="f21b5-136">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="f21b5-137">Привязки связаны с конечными точками с помощью сочетания атрибутов `name` и `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="f21b5-137">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="f21b5-138">Атрибут `name` описывает раздел, в котором определена привязка.</span><span class="sxs-lookup"><span data-stu-id="f21b5-138">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="f21b5-139">Атрибут `bindingConfiguration` указывает, какая конфигурация из раздела привязок используется.</span><span class="sxs-lookup"><span data-stu-id="f21b5-139">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="f21b5-140">В разделе привязки может определяться несколько конфигураций.</span><span class="sxs-lookup"><span data-stu-id="f21b5-140">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f21b5-141">Пример</span><span class="sxs-lookup"><span data-stu-id="f21b5-141">Example</span></span>  

 <span data-ttu-id="f21b5-142">Ниже приведен пример конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="f21b5-142">This is an example of a service configuration.</span></span>  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"
         name="HelloWorld">
  <endpoint address="/HelloWorld2/"
            name="test"
            bindingNamespace="http://www.cohowinery.com/"
            binding="basicHttpBinding"
            contract="IHelloWorld" />
</service>
```  
  
## <a name="see-also"></a><span data-ttu-id="f21b5-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f21b5-143">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="f21b5-144">Настройка служб</span><span class="sxs-lookup"><span data-stu-id="f21b5-144">Configuring Services</span></span>](../../../wcf/configuring-services.md)
