---
title: Элемент <alwaysFlowImpersonationPolicy>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
ms.openlocfilehash: 7c8ac37932a528ff0f000cbaab49124dec51b88c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154487"
---
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="f40fa-102">Элемент \<alwaysFlowImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="f40fa-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="f40fa-103">Указывает, что удостоверение Windows всегда проходит через асинхронные точки, независимо от того, как было выполнено олицетворение.</span><span class="sxs-lookup"><span data-stu-id="f40fa-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**\  
  
## <a name="syntax"></a><span data-ttu-id="f40fa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f40fa-104">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f40fa-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f40fa-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f40fa-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f40fa-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f40fa-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f40fa-107">Attributes</span></span>  
  
|<span data-ttu-id="f40fa-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f40fa-108">Attribute</span></span>|<span data-ttu-id="f40fa-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f40fa-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="f40fa-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f40fa-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="f40fa-111">Указывает, проходит ли идентификация Windows между асинхронными точками.</span><span class="sxs-lookup"><span data-stu-id="f40fa-111">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f40fa-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="f40fa-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="f40fa-113">Значение</span><span class="sxs-lookup"><span data-stu-id="f40fa-113">Value</span></span>|<span data-ttu-id="f40fa-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f40fa-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="f40fa-115">Удостоверение Windows не передается через асинхронные точки, если олицетворение не выполняется через управляемые методы, такие как <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> .</span><span class="sxs-lookup"><span data-stu-id="f40fa-115">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="f40fa-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f40fa-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="f40fa-117">Удостоверение Windows всегда проходит через асинхронные точки независимо от того, как было выполнено олицетворение.</span><span class="sxs-lookup"><span data-stu-id="f40fa-117">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f40fa-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f40fa-118">Child Elements</span></span>  
 <span data-ttu-id="f40fa-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f40fa-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f40fa-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f40fa-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f40fa-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="f40fa-121">Element</span></span>|<span data-ttu-id="f40fa-122">Описание</span><span class="sxs-lookup"><span data-stu-id="f40fa-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f40fa-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f40fa-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f40fa-124">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="f40fa-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f40fa-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="f40fa-125">Remarks</span></span>  
 <span data-ttu-id="f40fa-126">В .NET Framework версиях 1,0 и 1,1 идентификатор Windows не проходит через асинхронные точки.</span><span class="sxs-lookup"><span data-stu-id="f40fa-126">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="f40fa-127">В .NET Framework версии 2,0 имеется <xref:System.Threading.ExecutionContext> объект, который содержит сведения о выполняемом в данный момент потоке и передает его между асинхронными точками в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="f40fa-127">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="f40fa-128">Также передается <xref:System.Security.Principal.WindowsIdentity> как часть информации, которая проходит через асинхронные точки, при условии, что олицетворение достигается с помощью управляемых методов, таких как <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> , а не с помощью других средств, таких как вызов неуправляемого кода в машинные методы.</span><span class="sxs-lookup"><span data-stu-id="f40fa-128">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="f40fa-129">Этот элемент позволяет указать, что удостоверение Windows выполняет потоковую передачу через асинхронные точки независимо от того, как было достигнуто олицетворение.</span><span class="sxs-lookup"><span data-stu-id="f40fa-129">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="f40fa-130">Это поведение по умолчанию можно изменить двумя способами.</span><span class="sxs-lookup"><span data-stu-id="f40fa-130">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="f40fa-131">В управляемом коде на основе каждого потока.</span><span class="sxs-lookup"><span data-stu-id="f40fa-131">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="f40fa-132">Можно подавить поток на основе каждого потока, изменив <xref:System.Threading.ExecutionContext> Параметры и с <xref:System.Security.SecurityContext> помощью <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> метода, или <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f40fa-132">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="f40fa-133">В вызове неуправляемого интерфейса размещения для загрузки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f40fa-133">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="f40fa-134">Если для загрузки среды CLR используется неуправляемый интерфейс размещения (вместо простого управляемого исполняемого файла), можно указать специальный флаг в вызове функции [функции CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) .</span><span class="sxs-lookup"><span data-stu-id="f40fa-134">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="f40fa-135">Чтобы включить режим совместимости для всего процесса, задайте для `flags` параметра [CorBindToRuntimeEx функции](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) значение `STARTUP_ALWAYSFLOW_IMPERSONATION` .</span><span class="sxs-lookup"><span data-stu-id="f40fa-135">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="f40fa-136">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="f40fa-136">Configuration File</span></span>  
 <span data-ttu-id="f40fa-137">В приложении .NET Framework этот элемент можно использовать только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="f40fa-137">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="f40fa-138">Для приложения ASP.NET поток олицетворения можно настроить в файле aspnet. config, который находится в \<Windows Folder> каталоге \микрософт.нет\фрамеворк\вкс.КС.кскскскс.</span><span class="sxs-lookup"><span data-stu-id="f40fa-138">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="f40fa-139">ASP.NET по умолчанию отключает поток олицетворения в файле aspnet. config, используя следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="f40fa-139">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="f40fa-140">В ASP.NET, если требуется разрешить поток олицетворения, необходимо явно использовать следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="f40fa-140">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="f40fa-141">Пример</span><span class="sxs-lookup"><span data-stu-id="f40fa-141">Example</span></span>  
 <span data-ttu-id="f40fa-142">В следующем примере показано, как указать, что удостоверение Windows проходит через асинхронные точки, даже если олицетворение достигается через средства, отличные от управляемых методов.</span><span class="sxs-lookup"><span data-stu-id="f40fa-142">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f40fa-143">См. также</span><span class="sxs-lookup"><span data-stu-id="f40fa-143">See also</span></span>

- [<span data-ttu-id="f40fa-144">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="f40fa-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f40fa-145">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="f40fa-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f40fa-146">\<legacyImpersonationPolicy>Дерев</span><span class="sxs-lookup"><span data-stu-id="f40fa-146">\<legacyImpersonationPolicy> Element</span></span>](legacyimpersonationpolicy-element.md)
