---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: c12f57d68de870123d92c8a101e2999c24bb988f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855019"
---
# \<service>
<span data-ttu-id="c798c-101">Элемент `service` содержит параметры для службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c798c-101">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="c798c-102">Он также содержит конечные точки, предоставляющие доступ к службе.</span><span class="sxs-lookup"><span data-stu-id="c798c-102">It also contains endpoints that expose the service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<service>**  
  
## <a name="syntax"></a><span data-ttu-id="c798c-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c798c-103">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c798c-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c798c-104">Attributes and Elements</span></span>  
 <span data-ttu-id="c798c-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c798c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c798c-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c798c-106">Attributes</span></span>  
  
|<span data-ttu-id="c798c-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c798c-107">Attribute</span></span>|<span data-ttu-id="c798c-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="c798c-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c798c-109">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="c798c-109">behaviorConfiguration</span></span>|<span data-ttu-id="c798c-110">Строка, содержащая имя поведения, которое следует использовать для создания экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="c798c-110">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="c798c-111">Имя поведения должно входить в область действия в точке определения службы.</span><span class="sxs-lookup"><span data-stu-id="c798c-111">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="c798c-112">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="c798c-112">The default value is an empty string.</span></span>|  
|<span data-ttu-id="c798c-113">name</span><span class="sxs-lookup"><span data-stu-id="c798c-113">name</span></span>|<span data-ttu-id="c798c-114">Требуемый строковый атрибут, указывающий тип службы, экземпляр которой создается.</span><span class="sxs-lookup"><span data-stu-id="c798c-114">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="c798c-115">Этот параметр должен иметь значение допустимого типа.</span><span class="sxs-lookup"><span data-stu-id="c798c-115">This setting must equate to a valid type.</span></span> <span data-ttu-id="c798c-116">Формат должен быть `Namespace.Class.`.</span><span class="sxs-lookup"><span data-stu-id="c798c-116">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c798c-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c798c-117">Child Elements</span></span>  
  
|<span data-ttu-id="c798c-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="c798c-118">Element</span></span>|<span data-ttu-id="c798c-119">Описание</span><span class="sxs-lookup"><span data-stu-id="c798c-119">Description</span></span>|  
|-------------|-----------------|  
|[\<endpoint>](endpoint-element.md)|<span data-ttu-id="c798c-120">Коллекция элементов `endpoint`, которые обеспечивают доступ к данной службе.</span><span class="sxs-lookup"><span data-stu-id="c798c-120">A collection of `endpoint` elements that expose this service.</span></span>|  
|[\<host>](host.md)|<span data-ttu-id="c798c-121">Задает узел данного экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="c798c-121">Specifies the host of this service instance.</span></span> <span data-ttu-id="c798c-122">Это элемент типа <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="c798c-122">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c798c-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c798c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c798c-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="c798c-124">Element</span></span>|<span data-ttu-id="c798c-125">Описание</span><span class="sxs-lookup"><span data-stu-id="c798c-125">Description</span></span>|  
|-------------|-----------------|  
|[\<services>](services.md)|<span data-ttu-id="c798c-126">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="c798c-126">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c798c-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="c798c-127">Remarks</span></span>  
 <span data-ttu-id="c798c-128">Службы задаются в разделе `services` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c798c-128">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="c798c-129">Сборка может содержать любое число служб.</span><span class="sxs-lookup"><span data-stu-id="c798c-129">An assembly can contain any number of services.</span></span> <span data-ttu-id="c798c-130">Для каждой службы используется собственный раздел конфигурации `service`.</span><span class="sxs-lookup"><span data-stu-id="c798c-130">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="c798c-131">В этом разделе определяются контракт, поведение и конечные точки конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="c798c-131">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="c798c-132">Элемент `behaviorConfiguration` также является необязательным.</span><span class="sxs-lookup"><span data-stu-id="c798c-132">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="c798c-133">Он указывает поведение, используемое службой.</span><span class="sxs-lookup"><span data-stu-id="c798c-133">It identifies the behavior the service uses.</span></span> <span data-ttu-id="c798c-134">Поведение, заданное в данном атрибуте, должно быть связано с поведением в области в том же файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c798c-134">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="c798c-135">Каждая служба предоставляет доступ к одной или нескольким конечным точкам, которые имеют собственные адреса и привязки.</span><span class="sxs-lookup"><span data-stu-id="c798c-135">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="c798c-136">Все привязки в файле конфигурации должны быть определены в области файла.</span><span class="sxs-lookup"><span data-stu-id="c798c-136">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="c798c-137">Привязки связаны с конечными точками с помощью сочетания атрибутов `name` и `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="c798c-137">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="c798c-138">Атрибут `name` описывает раздел, в котором определена привязка.</span><span class="sxs-lookup"><span data-stu-id="c798c-138">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="c798c-139">Атрибут `bindingConfiguration` указывает, какая конфигурация из раздела привязок используется.</span><span class="sxs-lookup"><span data-stu-id="c798c-139">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="c798c-140">В разделе привязки может определяться несколько конфигураций.</span><span class="sxs-lookup"><span data-stu-id="c798c-140">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c798c-141">Пример</span><span class="sxs-lookup"><span data-stu-id="c798c-141">Example</span></span>  
 <span data-ttu-id="c798c-142">Ниже приведен пример конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="c798c-142">This is an example of a service configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c798c-143">См. также</span><span class="sxs-lookup"><span data-stu-id="c798c-143">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="c798c-144">Настройка служб</span><span class="sxs-lookup"><span data-stu-id="c798c-144">Configuring Services</span></span>](../../../wcf/configuring-services.md)
