---
title: Элемент <PreferComInsteadOfManagedRemoting>
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
ms.openlocfilehash: 1376df4efd56734f2b8da9bd76033afcce8a285b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "77452257"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="dcff1-102">Элемент \<PreferComInsteadOfManagedRemoting></span><span class="sxs-lookup"><span data-stu-id="dcff1-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="dcff1-103">Указывает, будет ли среда выполнения использовать COM-взаимодействие вместо удаленного взаимодействия для всех вызовов через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="dcff1-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<PreferComInsteadOfManagedRemoting>**  
  
## <a name="syntax"></a><span data-ttu-id="dcff1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dcff1-104">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dcff1-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dcff1-105">Attributes and Elements</span></span>  
 <span data-ttu-id="dcff1-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dcff1-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dcff1-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dcff1-107">Attributes</span></span>  
  
|<span data-ttu-id="dcff1-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dcff1-108">Attribute</span></span>|<span data-ttu-id="dcff1-109">Описание</span><span class="sxs-lookup"><span data-stu-id="dcff1-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="dcff1-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="dcff1-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="dcff1-111">Указывает, будет ли среда выполнения использовать COM-взаимодействие вместо удаленного взаимодействия через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="dcff1-111">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="dcff1-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="dcff1-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="dcff1-113">Значение</span><span class="sxs-lookup"><span data-stu-id="dcff1-113">Value</span></span>|<span data-ttu-id="dcff1-114">Описание</span><span class="sxs-lookup"><span data-stu-id="dcff1-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="dcff1-115">Среда выполнения будет использовать удаленное взаимодействие через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="dcff1-115">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="dcff1-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dcff1-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="dcff1-117">Среда выполнения будет использовать COM-взаимодействие через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="dcff1-117">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dcff1-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dcff1-118">Child Elements</span></span>  
 <span data-ttu-id="dcff1-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dcff1-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dcff1-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dcff1-120">Parent Elements</span></span>  
  
|<span data-ttu-id="dcff1-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="dcff1-121">Element</span></span>|<span data-ttu-id="dcff1-122">Описание</span><span class="sxs-lookup"><span data-stu-id="dcff1-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="dcff1-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dcff1-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="dcff1-124">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="dcff1-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dcff1-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="dcff1-125">Remarks</span></span>  
 <span data-ttu-id="dcff1-126">Если `enabled` для атрибута задано значение `true` , среда выполнения ведет себя следующим образом:</span><span class="sxs-lookup"><span data-stu-id="dcff1-126">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="dcff1-127">Среда выполнения не вызывает [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) для интерфейса [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) , когда интерфейс [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) входит в домен через интерфейс COM.</span><span class="sxs-lookup"><span data-stu-id="dcff1-127">The runtime does not call [IUnknown::QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="dcff1-128">Вместо этого он формирует [вызываемую оболочку времени выполнения](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) вокруг объекта.</span><span class="sxs-lookup"><span data-stu-id="dcff1-128">Instead, it constructs a [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="dcff1-129">Среда выполнения возвращает E_NOINTERFACE при получении `QueryInterface` вызова для интерфейса [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) для любой [вызываемой оболочки com](../../../../standard/native-interop/com-callable-wrapper.md) (CCW), созданной в этом домене.</span><span class="sxs-lookup"><span data-stu-id="dcff1-129">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="dcff1-130">Эти два поведения гарантируют, что все вызовы через COM-интерфейсы между управляемыми объектами в границах доменов приложений используют COM и COM-взаимодействие вместо удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="dcff1-130">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcff1-131">Пример</span><span class="sxs-lookup"><span data-stu-id="dcff1-131">Example</span></span>  
 <span data-ttu-id="dcff1-132">В следующем примере показано, как указать, что среда выполнения должна использовать COM-взаимодействие через границы изоляции:</span><span class="sxs-lookup"><span data-stu-id="dcff1-132">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dcff1-133">См. также</span><span class="sxs-lookup"><span data-stu-id="dcff1-133">See also</span></span>

- [<span data-ttu-id="dcff1-134">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="dcff1-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="dcff1-135">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="dcff1-135">Configuration File Schema</span></span>](../index.md)
