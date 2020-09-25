---
title: Элемент <legacyImpersonationPolicy>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
ms.openlocfilehash: ca10c809ddf319817aaa074ba5fc3415abf6387d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192520"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="733a7-102">Элемент \<legacyImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="733a7-102">\<legacyImpersonationPolicy> Element</span></span>

<span data-ttu-id="733a7-103">Указывает, что удостоверение Windows не проходит через асинхронные точки, независимо от параметров потока для контекста выполнения в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="733a7-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="733a7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="733a7-104">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="733a7-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="733a7-105">Attributes and Elements</span></span>  

 <span data-ttu-id="733a7-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="733a7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="733a7-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="733a7-107">Attributes</span></span>  
  
|<span data-ttu-id="733a7-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="733a7-108">Attribute</span></span>|<span data-ttu-id="733a7-109">Описание</span><span class="sxs-lookup"><span data-stu-id="733a7-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="733a7-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="733a7-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="733a7-111">Указывает, что объект не передается <xref:System.Security.Principal.WindowsIdentity> по асинхронным точкам, независимо от <xref:System.Threading.ExecutionContext> параметров потока в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="733a7-111">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="733a7-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="733a7-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="733a7-113">Значение</span><span class="sxs-lookup"><span data-stu-id="733a7-113">Value</span></span>|<span data-ttu-id="733a7-114">Описание</span><span class="sxs-lookup"><span data-stu-id="733a7-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="733a7-115"><xref:System.Security.Principal.WindowsIdentity> проходит через асинхронные точки в зависимости от <xref:System.Threading.ExecutionContext> параметров потока для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="733a7-115"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="733a7-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="733a7-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="733a7-117"><xref:System.Security.Principal.WindowsIdentity> не перетекает через асинхронные точки, независимо от <xref:System.Threading.ExecutionContext> параметров потока в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="733a7-117"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="733a7-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="733a7-118">Child Elements</span></span>  

 <span data-ttu-id="733a7-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="733a7-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="733a7-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="733a7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="733a7-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="733a7-121">Element</span></span>|<span data-ttu-id="733a7-122">Описание</span><span class="sxs-lookup"><span data-stu-id="733a7-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="733a7-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="733a7-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="733a7-124">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="733a7-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="733a7-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="733a7-125">Remarks</span></span>  

 <span data-ttu-id="733a7-126">В .NET Framework версиях 1,0 и 1,1, объект не <xref:System.Security.Principal.WindowsIdentity> проходит через определенные пользователем асинхронные точки.</span><span class="sxs-lookup"><span data-stu-id="733a7-126">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="733a7-127">Начиная с версии .NET Framework 2,0, существует <xref:System.Threading.ExecutionContext> объект, который содержит сведения о выполняющемся в данный момент потоке и проходит через асинхронные точки в пределах домена приложения.</span><span class="sxs-lookup"><span data-stu-id="733a7-127">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="733a7-128"><xref:System.Security.Principal.WindowsIdentity>Включается в этот контекст выполнения и, следовательно, проходит через асинхронные точки, что означает, что если контекст олицетворения существует, он также будет работать.</span><span class="sxs-lookup"><span data-stu-id="733a7-128">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="733a7-129">Начиная с .NET Framework 2,0, можно использовать `<legacyImpersonationPolicy>` элемент, чтобы указать, что не передается  <xref:System.Security.Principal.WindowsIdentity> через асинхронные точки.</span><span class="sxs-lookup"><span data-stu-id="733a7-129">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="733a7-130">Общеязыковая среда выполнения (CLR) осведомлена об операциях олицетворения, выполняемых только с помощью управляемого кода, а не олицетворения, выполненных за пределами управляемого кода, например посредством вызова неуправляемого кода платформой или прямых вызовов функций Win32.</span><span class="sxs-lookup"><span data-stu-id="733a7-130">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="733a7-131">Только управляемые <xref:System.Security.Principal.WindowsIdentity> объекты могут передаваться по асинхронным точкам, если только `alwaysFlowImpersonationPolicy` элемент не имеет значение true ( `<alwaysFlowImpersonationPolicy enabled="true"/>` ).</span><span class="sxs-lookup"><span data-stu-id="733a7-131">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="733a7-132">Если задать `alwaysFlowImpersonationPolicy` для элемента значение true, удостоверение Windows всегда проходит через асинхронные точки независимо от того, как было выполнено олицетворение.</span><span class="sxs-lookup"><span data-stu-id="733a7-132">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="733a7-133">Дополнительные сведения о передаче неуправляемого олицетворения через асинхронные точки см. в разделе [ \<alwaysFlowImpersonationPolicy> element](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="733a7-133">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="733a7-134">Это поведение по умолчанию можно изменить двумя способами.</span><span class="sxs-lookup"><span data-stu-id="733a7-134">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="733a7-135">В управляемом коде на основе каждого потока.</span><span class="sxs-lookup"><span data-stu-id="733a7-135">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="733a7-136">Можно подавить поток на основе каждого потока, изменив <xref:System.Threading.ExecutionContext> Параметры и с <xref:System.Security.SecurityContext> помощью <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> метода, или <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="733a7-136">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="733a7-137">В вызове неуправляемого интерфейса размещения для загрузки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="733a7-137">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="733a7-138">Если для загрузки среды CLR используется неуправляемый интерфейс размещения (вместо простого управляемого исполняемого файла), можно указать специальный флаг в вызове функции [функции CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) .</span><span class="sxs-lookup"><span data-stu-id="733a7-138">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="733a7-139">Чтобы включить режим совместимости для всего процесса, присвойте `flags` параметру [функции CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) значение STARTUP_LEGACY_IMPERSONATION.</span><span class="sxs-lookup"><span data-stu-id="733a7-139">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="733a7-140">Дополнительные сведения см. в описании [ \<alwaysFlowImpersonationPolicy> элемента](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="733a7-140">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="733a7-141">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="733a7-141">Configuration File</span></span>  

 <span data-ttu-id="733a7-142">В приложении .NET Framework этот элемент можно использовать только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="733a7-142">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="733a7-143">Для приложения ASP.NET поток олицетворения можно настроить в файле aspnet.config, который находится в \<Windows Folder> каталоге \микрософт.нет\фрамеворк\вкс.КС.кскскскс.</span><span class="sxs-lookup"><span data-stu-id="733a7-143">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="733a7-144">ASP.NET по умолчанию отключает поток олицетворения в файле aspnet.config с помощью следующих параметров конфигурации:</span><span class="sxs-lookup"><span data-stu-id="733a7-144">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="733a7-145">В ASP.NET, если требуется разрешить поток олицетворения, необходимо явно использовать следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="733a7-145">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="733a7-146">Пример</span><span class="sxs-lookup"><span data-stu-id="733a7-146">Example</span></span>  

 <span data-ttu-id="733a7-147">В следующем примере показано, как задать устаревшее поведение, которое не пополняет удостоверение Windows в асинхронных точках.</span><span class="sxs-lookup"><span data-stu-id="733a7-147">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="733a7-148">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="733a7-148">See also</span></span>

- [<span data-ttu-id="733a7-149">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="733a7-149">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="733a7-150">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="733a7-150">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="733a7-151">\<alwaysFlowImpersonationPolicy> Элемент</span><span class="sxs-lookup"><span data-stu-id="733a7-151">\<alwaysFlowImpersonationPolicy> Element</span></span>](alwaysflowimpersonationpolicy-element.md)
