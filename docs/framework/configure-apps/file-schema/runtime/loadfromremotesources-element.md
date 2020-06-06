---
title: Элемент <loadFromRemoteSources>
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: a0dcffe378cdd09de0fbd8f0a6ef0635c033fd9c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154066"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="f23c5-102">Элемент \<loadFromRemoteSources></span><span class="sxs-lookup"><span data-stu-id="f23c5-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="f23c5-103">Указывает, должны ли сборки, загруженные из удаленных источников, предоставлять полное доверие в .NET Framework 4 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f23c5-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f23c5-104">Если вы перенаправлялись на эту статью из-за сообщения об ошибке в списке ошибок проекта Visual Studio или ошибки сборки, см. раздел [как использовать сборку из Интернета в Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f23c5-104">If you were directed to this article because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**  
  
## <a name="syntax"></a><span data-ttu-id="f23c5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f23c5-105">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f23c5-106">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="f23c5-106">Attributes and elements</span></span>
 <span data-ttu-id="f23c5-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f23c5-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f23c5-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f23c5-108">Attributes</span></span>  
  
|<span data-ttu-id="f23c5-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f23c5-109">Attribute</span></span>|<span data-ttu-id="f23c5-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f23c5-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="f23c5-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f23c5-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="f23c5-112">Указывает, должно ли быть предоставлено полное доверие для сборки, загружаемой из удаленного источника.</span><span class="sxs-lookup"><span data-stu-id="f23c5-112">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f23c5-113">Включенный атрибут</span><span class="sxs-lookup"><span data-stu-id="f23c5-113">enabled attribute</span></span>  
  
|<span data-ttu-id="f23c5-114">Значение</span><span class="sxs-lookup"><span data-stu-id="f23c5-114">Value</span></span>|<span data-ttu-id="f23c5-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f23c5-115">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="f23c5-116">Не предоставляйте полное доверие приложениям из удаленных источников.</span><span class="sxs-lookup"><span data-stu-id="f23c5-116">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="f23c5-117">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f23c5-117">This is the default.</span></span>|  
|`true`|<span data-ttu-id="f23c5-118">Предоставление полного доверия приложениям из удаленных источников.</span><span class="sxs-lookup"><span data-stu-id="f23c5-118">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f23c5-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f23c5-119">Child elements</span></span>  
 <span data-ttu-id="f23c5-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f23c5-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f23c5-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f23c5-121">Parent elements</span></span>  
  
|<span data-ttu-id="f23c5-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="f23c5-122">Element</span></span>|<span data-ttu-id="f23c5-123">Описание</span><span class="sxs-lookup"><span data-stu-id="f23c5-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f23c5-124">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f23c5-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f23c5-125">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f23c5-125">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f23c5-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="f23c5-126">Remarks</span></span>

<span data-ttu-id="f23c5-127">В .NET Framework 3,5 и более ранних версиях при загрузке сборки из удаленного расположения код в сборке выполняется в режиме частичного доверия с набором разрешений, зависящим от зоны, из которой она загружена.</span><span class="sxs-lookup"><span data-stu-id="f23c5-127">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="f23c5-128">Например, если загрузить сборку с веб-сайта, она загружается в зону Интернета и предоставляет набор разрешений Интернета.</span><span class="sxs-lookup"><span data-stu-id="f23c5-128">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="f23c5-129">Иными словами, он выполняется в песочнице Интернета.</span><span class="sxs-lookup"><span data-stu-id="f23c5-129">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="f23c5-130">Начиная с .NET Framework 4, политика разграничения доступа кода (CAS) отключена, и сборки загружаются с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="f23c5-130">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="f23c5-131">Обычно это обеспечивает полное доверие сборкам, загруженным с помощью <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> ранее изолированного метода.</span><span class="sxs-lookup"><span data-stu-id="f23c5-131">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="f23c5-132">Чтобы предотвратить это, возможность запуска кода в сборках, загружаемых из удаленного источника, по умолчанию отключена.</span><span class="sxs-lookup"><span data-stu-id="f23c5-132">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="f23c5-133">По умолчанию при попытке загрузить удаленную сборку <xref:System.IO.FileLoadException> выдается сообщение об исключении, подобное следующему:</span><span class="sxs-lookup"><span data-stu-id="f23c5-133">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

<span data-ttu-id="f23c5-134">Для загрузки сборки и выполнения ее кода необходимо выполнить одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="f23c5-134">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="f23c5-135">Явно Создайте песочницу для сборки (см. раздел [как запустить частично доверенный код в песочнице](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span><span class="sxs-lookup"><span data-stu-id="f23c5-135">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="f23c5-136">Запустите код сборки в режиме полного доверия.</span><span class="sxs-lookup"><span data-stu-id="f23c5-136">Run the assembly's code in full trust.</span></span> <span data-ttu-id="f23c5-137">Для этого нужно настроить `<loadFromRemoteSources>` элемент.</span><span class="sxs-lookup"><span data-stu-id="f23c5-137">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="f23c5-138">Он позволяет указать, что сборки, выполняемые в режиме частичного доверия в более ранних версиях .NET Framework теперь выполняются с полным доверием в .NET Framework 4 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="f23c5-138">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f23c5-139">Если сборка не должна выполняться с полным доверием, не устанавливайте этот элемент конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f23c5-139">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="f23c5-140">Вместо этого создайте изолированную среду, <xref:System.AppDomain> в которой будет загружена сборка.</span><span class="sxs-lookup"><span data-stu-id="f23c5-140">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="f23c5-141">`enabled`Атрибут для `<loadFromRemoteSources>` элемента эффективен, только если отключена разграничение доступа кода (CAS).</span><span class="sxs-lookup"><span data-stu-id="f23c5-141">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="f23c5-142">По умолчанию политика CAS отключена в .NET Framework 4 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="f23c5-142">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="f23c5-143">Если задано `enabled` значение `true` , удаленным сборкам предоставляется полное доверие.</span><span class="sxs-lookup"><span data-stu-id="f23c5-143">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="f23c5-144">Если `enabled` параметр не имеет значение `true` , то <xref:System.IO.FileLoadException> исключение создается при любом из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="f23c5-144">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="f23c5-145">Поведение "песочницы" текущего домена отличается от поведения в .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="f23c5-145">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="f23c5-146">Для этого требуется отключить политику разграничения доступа, а текущий домен не должен быть изолирован.</span><span class="sxs-lookup"><span data-stu-id="f23c5-146">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="f23c5-147">Загружаемая сборка не принадлежит `MyComputer` зоне.</span><span class="sxs-lookup"><span data-stu-id="f23c5-147">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="f23c5-148">Установка `<loadFromRemoteSources>` элемента, чтобы `true` запретить возникновение этого исключения.</span><span class="sxs-lookup"><span data-stu-id="f23c5-148">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="f23c5-149">Он позволяет указать, что вы не полагаетесь на среду CLR для использования песочницы загруженными сборками для обеспечения безопасности и можете ли они быть разрешены для выполнения с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="f23c5-149">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="f23c5-150">Примечания</span><span class="sxs-lookup"><span data-stu-id="f23c5-150">Notes</span></span>

- <span data-ttu-id="f23c5-151">В .NET Framework 4,5 и более поздних версиях сборки на локальных сетевых ресурсах по умолчанию работают в режиме полного доверия. не нужно включать `<loadFromRemoteSources>` элемент.</span><span class="sxs-lookup"><span data-stu-id="f23c5-151">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="f23c5-152">Если приложение скопировано из Интернета, оно помечается ОС Windows как веб-приложение, даже если находится на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f23c5-152">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="f23c5-153">Это обозначение можно изменить, изменив его свойства файла, или с помощью `<loadFromRemoteSources>` элемента можно предоставить сборке полное доверие.</span><span class="sxs-lookup"><span data-stu-id="f23c5-153">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="f23c5-154">Также можно использовать метод <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A>, чтобы загрузить локальную сборку, которую операционная система пометила как загруженную из Интернета.</span><span class="sxs-lookup"><span data-stu-id="f23c5-154">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="f23c5-155">Вы можете получить <xref:System.IO.FileLoadException> в приложении, работающем в приложении Windows Virtual PC.</span><span class="sxs-lookup"><span data-stu-id="f23c5-155">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="f23c5-156">Это может произойти при попытке загрузить файл из связанных папок на компьютере размещения.</span><span class="sxs-lookup"><span data-stu-id="f23c5-156">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="f23c5-157">Это также может произойти при попытке загрузить файл из папки, связанной [службы удаленных рабочих столов](/windows/win32/termserv/terminal-services-portal) (службы терминалов).</span><span class="sxs-lookup"><span data-stu-id="f23c5-157">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](/windows/win32/termserv/terminal-services-portal) (Terminal Services).</span></span> <span data-ttu-id="f23c5-158">Чтобы избежать исключения, задайте для параметра значение `enabled` `true` .</span><span class="sxs-lookup"><span data-stu-id="f23c5-158">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="f23c5-159">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="f23c5-159">Configuration file</span></span>

<span data-ttu-id="f23c5-160">Этот элемент обычно используется в файле конфигурации приложения, но может использоваться в других файлах конфигурации в зависимости от контекста.</span><span class="sxs-lookup"><span data-stu-id="f23c5-160">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="f23c5-161">Дополнительные сведения см. в статье [более Неявное использование политики CAS: лоадфромремотесаурцес](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) в блоге по безопасности .NET.</span><span class="sxs-lookup"><span data-stu-id="f23c5-161">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="f23c5-162">Пример</span><span class="sxs-lookup"><span data-stu-id="f23c5-162">Example</span></span>

<span data-ttu-id="f23c5-163">В следующем примере показано, как предоставить полное доверие сборкам, загруженным из удаленных источников.</span><span class="sxs-lookup"><span data-stu-id="f23c5-163">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="f23c5-164">См. также</span><span class="sxs-lookup"><span data-stu-id="f23c5-164">See also</span></span>

- [<span data-ttu-id="f23c5-165">Более Неявное использование политики CAS: Лоадфромремотесаурцес</span><span class="sxs-lookup"><span data-stu-id="f23c5-165">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [<span data-ttu-id="f23c5-166">Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде</span><span class="sxs-lookup"><span data-stu-id="f23c5-166">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="f23c5-167">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="f23c5-167">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f23c5-168">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="f23c5-168">Configuration File Schema</span></span>](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
