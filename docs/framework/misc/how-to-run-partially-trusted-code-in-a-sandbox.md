---
title: Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде
description: Узнайте, как запустить частично доверенный код в песочнице в .NET. Класс AppDomain является эффективным средством изолирования управляемых приложений.
ms.date: 03/30/2017
helpviewer_keywords:
- partially trusted code
- sandboxing
- partial trust
- restricted security environment
- code security, sandboxing
ms.assetid: d1ad722b-5b49-4040-bff3-431b94bb8095
ms.openlocfilehash: 415a42f7c4f4866bb72f19bdd6f02bfdb5158bf8
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855807"
---
# <a name="how-to-run-partially-trusted-code-in-a-sandbox"></a><span data-ttu-id="1d759-104">Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде</span><span class="sxs-lookup"><span data-stu-id="1d759-104">How to: Run Partially Trusted Code in a Sandbox</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="1d759-105">Изолирование в песочнице — это способ запуска кода в ограниченной среде безопасности, ограничивающей разрешения доступа, предоставленные коду.</span><span class="sxs-lookup"><span data-stu-id="1d759-105">Sandboxing is the practice of running code in a restricted security environment, which limits the access permissions granted to the code.</span></span> <span data-ttu-id="1d759-106">Например, если имеется управляемая библиотека, полученная из источника с неполным доверием, не следует запускать ее как полностью доверенную.</span><span class="sxs-lookup"><span data-stu-id="1d759-106">For example, if you have a managed library from a source you do not completely trust, you should not run it as fully trusted.</span></span> <span data-ttu-id="1d759-107">Вместо этого следует поместить код в "песочницу", которая ограничивает разрешения кода, которые необходимы ему по вашему мнению (например, <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>).</span><span class="sxs-lookup"><span data-stu-id="1d759-107">Instead, you should place the code in a sandbox that limits its permissions to those that you expect it to need (for example, <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> permission).</span></span>  
  
 <span data-ttu-id="1d759-108">Изолирование в песочнице также можно использовать для тестирования кода, который будет распространяться для запуска в частично доверенных средах.</span><span class="sxs-lookup"><span data-stu-id="1d759-108">You can also use sandboxing to test code you will be distributing that will run in partially trusted environments.</span></span>  
  
 <span data-ttu-id="1d759-109">Использование объекта <xref:System.AppDomain> — это эффективный способ предоставления песочницы для управляемых приложений.</span><span class="sxs-lookup"><span data-stu-id="1d759-109">An <xref:System.AppDomain> is an effective way of providing a sandbox for managed applications.</span></span> <span data-ttu-id="1d759-110">Домены приложений, используемые для запуска частично доверенного кода, имеют разрешения, которые определяют защищенные ресурсы, доступные при запуске в этом домене <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="1d759-110">Application domains that are used for running partially trusted code have permissions that define the protected resources that are available when running within that <xref:System.AppDomain>.</span></span> <span data-ttu-id="1d759-111">Код, выполняемый в домене <xref:System.AppDomain>, ограничивается разрешениями для домена <xref:System.AppDomain> и может осуществлять доступ только к заданным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="1d759-111">Code that runs inside the <xref:System.AppDomain> is bound by the permissions associated with the <xref:System.AppDomain> and is allowed to access only the specified resources.</span></span> <span data-ttu-id="1d759-112">Домен <xref:System.AppDomain> также включает массив <xref:System.Security.Policy.StrongName>, используемый для определения сборок, которые необходимо загрузить как полностью доверенные.</span><span class="sxs-lookup"><span data-stu-id="1d759-112">The <xref:System.AppDomain> also includes a <xref:System.Security.Policy.StrongName> array that is used to identify assemblies that are to be loaded as fully trusted.</span></span> <span data-ttu-id="1d759-113">Это позволяет создателю домена <xref:System.AppDomain> запустить новый домен в песочнице, который разрешает выполнение определенных вспомогательных сборок с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="1d759-113">This enables the creator of an <xref:System.AppDomain> to start a new sandboxed domain that allows specific helper assemblies to be fully trusted.</span></span> <span data-ttu-id="1d759-114">Чтобы загрузить сборки в качестве полностью доверенных, можно также разместить их в глобальном кэше сборок. Однако в этом случае они загрузятся как полностью доверенные во всех доменах приложений, созданных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1d759-114">Another option for loading assemblies as fully trusted is to place them in the global assembly cache; however, that will load assemblies as fully trusted in all application domains created on that computer.</span></span> <span data-ttu-id="1d759-115">Список строгих имен позволяет принимать решение по каждому домену <xref:System.AppDomain>, что обеспечивает более точное определение.</span><span class="sxs-lookup"><span data-stu-id="1d759-115">The list of strong names supports a per-<xref:System.AppDomain> decision that provides more restrictive determination.</span></span>  
  
 <span data-ttu-id="1d759-116">Чтобы задать набор разрешений для приложений, выполняемых в песочнице, можно использовать перегрузку метода <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1d759-116">You can use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> method overload to specify the permission set for applications that run in a sandbox.</span></span> <span data-ttu-id="1d759-117">Она позволяет точно установить требуемый уровень управления доступом для кода.</span><span class="sxs-lookup"><span data-stu-id="1d759-117">This overload enables you to specify the exact level of code access security you want.</span></span> <span data-ttu-id="1d759-118">Сборки, загружаемые в <xref:System.AppDomain> с помощью этой перегрузки, могут иметь заданный набор прав или являться полностью доверенными.</span><span class="sxs-lookup"><span data-stu-id="1d759-118">Assemblies that are loaded into an <xref:System.AppDomain> by using this overload can either have the specified grant set only, or can be fully trusted.</span></span> <span data-ttu-id="1d759-119">Сборке предоставляется полное доверие, если она находится в глобальном кэше сборок или указана в параметре массива `fullTrustAssemblies` (<xref:System.Security.Policy.StrongName>).</span><span class="sxs-lookup"><span data-stu-id="1d759-119">The assembly is granted full trust if it is in the global assembly cache or listed in the `fullTrustAssemblies` (the <xref:System.Security.Policy.StrongName>) array parameter.</span></span> <span data-ttu-id="1d759-120">В список `fullTrustAssemblies` следует добавлять только сборки, о которых известно, что они являются полностью доверенными.</span><span class="sxs-lookup"><span data-stu-id="1d759-120">Only assemblies known to be fully trusted should be added to the `fullTrustAssemblies` list.</span></span>  
  
 <span data-ttu-id="1d759-121">Перегрузка имеет следующую подпись:</span><span class="sxs-lookup"><span data-stu-id="1d759-121">The overload has the following signature:</span></span>  
  
```csharp
AppDomain.CreateDomain( string friendlyName,  
                        Evidence securityInfo,  
                        AppDomainSetup info,  
                        PermissionSet grantSet,  
                        params StrongName[] fullTrustAssemblies);  
```  
  
 <span data-ttu-id="1d759-122">Параметры перегрузки метода <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> задают имя домена <xref:System.AppDomain>, свидетельство для домена <xref:System.AppDomain>, объект <xref:System.AppDomainSetup>, определяющий базовую папку приложения для песочницы, используемый набор разрешений и строгие имена для полностью доверенных сборок.</span><span class="sxs-lookup"><span data-stu-id="1d759-122">The parameters for the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> method overload specify the name of the <xref:System.AppDomain>, the evidence for the <xref:System.AppDomain>, the <xref:System.AppDomainSetup> object that identifies the application base for the sandbox, the permission set to use, and the strong names for fully trusted assemblies.</span></span>  
  
 <span data-ttu-id="1d759-123">По соображениям безопасности базовая папка приложения, указанная в параметре `info`, не должна совпадать с базовой папкой ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="1d759-123">For security reasons, the application base specified in the `info` parameter should not be the application base for the hosting application.</span></span>  
  
 <span data-ttu-id="1d759-124">В качестве значения параметра `grantSet` можно задать либо явным образом созданный набор разрешений, либо стандартный набор разрешений, созданный методом <xref:System.Security.SecurityManager.GetStandardSandbox%2A>.</span><span class="sxs-lookup"><span data-stu-id="1d759-124">For the `grantSet` parameter, you can specify either a permission set you have explicitly created, or a standard permission set created by the <xref:System.Security.SecurityManager.GetStandardSandbox%2A> method.</span></span>  
  
 <span data-ttu-id="1d759-125">В отличие от большинства перегрузок <xref:System.AppDomain>, свидетельство для домена <xref:System.AppDomain> (предоставляемое параметром `securityInfo`) не используется для определения набора прав, предоставленного частично доверенным сборкам.</span><span class="sxs-lookup"><span data-stu-id="1d759-125">Unlike most <xref:System.AppDomain> loads, the evidence for the <xref:System.AppDomain> (which is provided by the `securityInfo` parameter) is not used to determine the grant set for the partially trusted assemblies.</span></span> <span data-ttu-id="1d759-126">Этот набор определяется независимо с помощью параметра `grantSet`.</span><span class="sxs-lookup"><span data-stu-id="1d759-126">Instead, it is independently specified by the `grantSet` parameter.</span></span> <span data-ttu-id="1d759-127">Однако свидетельство можно использовать в иных целях, например для определения области изолированного хранилища.</span><span class="sxs-lookup"><span data-stu-id="1d759-127">However, the evidence can be used for other purposes such as determining the isolated storage scope.</span></span>  
  
### <a name="to-run-an-application-in-a-sandbox"></a><span data-ttu-id="1d759-128">Запуск приложения в песочнице</span><span class="sxs-lookup"><span data-stu-id="1d759-128">To run an application in a sandbox</span></span>  
  
1. <span data-ttu-id="1d759-129">Создайте набор разрешений, которые нужно предоставить ненадежному приложению.</span><span class="sxs-lookup"><span data-stu-id="1d759-129">Create the permission set to be granted to the untrusted application.</span></span> <span data-ttu-id="1d759-130">Минимальное разрешение, которое можно предоставить, — <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>.</span><span class="sxs-lookup"><span data-stu-id="1d759-130">The minimum permission you can grant is <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> permission.</span></span> <span data-ttu-id="1d759-131">Кроме того, можно предоставить дополнительные разрешения, которые, по вашему мнению, будут безопасными для ненадежного кода, например разрешение <xref:System.Security.Permissions.IsolatedStorageFilePermission>.</span><span class="sxs-lookup"><span data-stu-id="1d759-131">You can also grant additional permissions you think might be safe for untrusted code; for example, <xref:System.Security.Permissions.IsolatedStorageFilePermission>.</span></span> <span data-ttu-id="1d759-132">Во фрагменте кода ниже показано создание набора разрешений, в котором содержится только одно разрешение <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>.</span><span class="sxs-lookup"><span data-stu-id="1d759-132">The following code creates a new permission set with only <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> permission.</span></span>  
  
    ```csharp
    PermissionSet permSet = new PermissionSet(PermissionState.None);  
    permSet.AddPermission(new SecurityPermission(SecurityPermissionFlag.Execution));  
    ```  
  
     <span data-ttu-id="1d759-133">Также можно использовать существующий именованный набор разрешений, например Internet.</span><span class="sxs-lookup"><span data-stu-id="1d759-133">Alternatively, you can use an existing named permission set, such as Internet.</span></span>  
  
    ```csharp
    Evidence ev = new Evidence();  
    ev.AddHostEvidence(new Zone(SecurityZone.Internet));  
    PermissionSet internetPS = SecurityManager.GetStandardSandbox(ev);  
    ```  
  
     <span data-ttu-id="1d759-134">Метод <xref:System.Security.SecurityManager.GetStandardSandbox%2A> возвращает набор разрешений `Internet` или `LocalIntranet` в зависимости от зоны в свидетельстве.</span><span class="sxs-lookup"><span data-stu-id="1d759-134">The <xref:System.Security.SecurityManager.GetStandardSandbox%2A> method returns either an `Internet` permission set or a `LocalIntranet` permission set depending on the zone in the evidence.</span></span> <span data-ttu-id="1d759-135">Метод <xref:System.Security.SecurityManager.GetStandardSandbox%2A> также создает разрешения идентификации для некоторых объектов свидетельства, переданных по ссылке.</span><span class="sxs-lookup"><span data-stu-id="1d759-135"><xref:System.Security.SecurityManager.GetStandardSandbox%2A> also constructs identity permissions for some of the evidence objects passed as references.</span></span>  
  
2. <span data-ttu-id="1d759-136">Подпишите сборку, которая содержит размещающий класс (в этом примере это класс `Sandboxer`), вызывающий ненадежный код.</span><span class="sxs-lookup"><span data-stu-id="1d759-136">Sign the assembly that contains the hosting class (named `Sandboxer` in this example) that calls the untrusted code.</span></span> <span data-ttu-id="1d759-137">Добавьте объект <xref:System.Security.Policy.StrongName>, используемый для подписания сборки, в массив <xref:System.Security.Policy.StrongName> в параметре `fullTrustAssemblies` вызова метода <xref:System.AppDomain.CreateDomain%2A>.</span><span class="sxs-lookup"><span data-stu-id="1d759-137">Add the <xref:System.Security.Policy.StrongName> used to sign the assembly to the <xref:System.Security.Policy.StrongName> array of the `fullTrustAssemblies` parameter of the <xref:System.AppDomain.CreateDomain%2A> call.</span></span> <span data-ttu-id="1d759-138">Чтобы разрешить выполнение кода с частичным доверием или предложить службы приложению с частичным доверием, нужно запустить размещающий класс как полностью доверенный.</span><span class="sxs-lookup"><span data-stu-id="1d759-138">The hosting class must run as fully trusted to enable the execution of the partial-trust code or to offer services to the partial-trust application.</span></span> <span data-ttu-id="1d759-139">Ниже показано, как читается строгое имя <xref:System.Security.Policy.StrongName> сборки.</span><span class="sxs-lookup"><span data-stu-id="1d759-139">This is how you read the <xref:System.Security.Policy.StrongName> of an assembly:</span></span>  
  
    ```csharp
    StrongName fullTrustAssembly = typeof(Sandboxer).Assembly.Evidence.GetHostEvidence<StrongName>();  
    ```  
  
     <span data-ttu-id="1d759-140">Сборки .NET Framework, такие как mscorlib и System.dll, не обязательно добавлять в список полностью доверенных сборок, так как они загружаются как полностью доверенные из глобального кэша сборок.</span><span class="sxs-lookup"><span data-stu-id="1d759-140">.NET Framework assemblies such as mscorlib and System.dll do not have to be added to the full-trust list because they are loaded as fully trusted from the global assembly cache.</span></span>  
  
3. <span data-ttu-id="1d759-141">Инициализируйте параметр <xref:System.AppDomainSetup> метода <xref:System.AppDomain.CreateDomain%2A>.</span><span class="sxs-lookup"><span data-stu-id="1d759-141">Initialize the <xref:System.AppDomainSetup> parameter of the <xref:System.AppDomain.CreateDomain%2A> method.</span></span> <span data-ttu-id="1d759-142">С помощью этого параметра можно управлять многими настройками нового домена <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="1d759-142">With this parameter, you can control many of the settings of the new <xref:System.AppDomain>.</span></span> <span data-ttu-id="1d759-143">Свойство <xref:System.AppDomainSetup.ApplicationBase%2A> является важной настройкой и должно отличаться от свойства <xref:System.AppDomainSetup.ApplicationBase%2A> домена <xref:System.AppDomain> основного приложения.</span><span class="sxs-lookup"><span data-stu-id="1d759-143">The <xref:System.AppDomainSetup.ApplicationBase%2A> property is an important setting, and should be different from the <xref:System.AppDomainSetup.ApplicationBase%2A> property for the <xref:System.AppDomain> of the hosting application.</span></span> <span data-ttu-id="1d759-144">Если значения <xref:System.AppDomainSetup.ApplicationBase%2A> совпадают, частично доверенное приложение может заставить ведущее приложение загрузить (как полностью доверенное) определяемое им исключение, тем самым создав угрозу безопасности.</span><span class="sxs-lookup"><span data-stu-id="1d759-144">If the <xref:System.AppDomainSetup.ApplicationBase%2A> settings are the same, the partial-trust application can get the hosting application to load (as fully trusted) an exception it defines, thus exploiting it.</span></span> <span data-ttu-id="1d759-145">Это еще одна причина, по которой не рекомендуется выполнять перехват исключения.</span><span class="sxs-lookup"><span data-stu-id="1d759-145">This is another reason why a catch (exception) is not recommended.</span></span> <span data-ttu-id="1d759-146">Чтобы снизить риск злоумышленного использования, необходимо задать для основного и изолированного приложений разные базовые папки.</span><span class="sxs-lookup"><span data-stu-id="1d759-146">Setting the application base of the host differently from the application base of the sandboxed application mitigates the risk of exploits.</span></span>  
  
    ```csharp
    AppDomainSetup adSetup = new AppDomainSetup();  
    adSetup.ApplicationBase = Path.GetFullPath(pathToUntrusted);  
    ```  
  
4. <span data-ttu-id="1d759-147">Чтобы создать домен приложения с использованием заданных параметров, вызовите перегрузку метода <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29>.</span><span class="sxs-lookup"><span data-stu-id="1d759-147">Call the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> method overload to create the application domain using the parameters we have specified.</span></span>  
  
     <span data-ttu-id="1d759-148">Подпись этого метода следующая:</span><span class="sxs-lookup"><span data-stu-id="1d759-148">The signature for this method is:</span></span>  
  
    ```csharp
    public static AppDomain CreateDomain(string friendlyName,
        Evidence securityInfo, AppDomainSetup info, PermissionSet grantSet,
        params StrongName[] fullTrustAssemblies)  
    ```  
  
     <span data-ttu-id="1d759-149">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="1d759-149">Additional information:</span></span>  
  
    - <span data-ttu-id="1d759-150">Это единственная перегрузка метода <xref:System.AppDomain.CreateDomain%2A>, принимающая в качестве параметра набор разрешений <xref:System.Security.PermissionSet>, то есть единственная перегрузка, позволяющая загружать приложение в режиме частичного доверия.</span><span class="sxs-lookup"><span data-stu-id="1d759-150">This is the only overload of the <xref:System.AppDomain.CreateDomain%2A> method that takes a <xref:System.Security.PermissionSet> as a parameter, and thus the only overload that lets you load an application in a partial-trust setting.</span></span>  
  
    - <span data-ttu-id="1d759-151">Параметр `evidence` не используется для вычисления набора разрешений. Он служит для идентификации другими компонентами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1d759-151">The `evidence` parameter is not used to calculate a permission set; it is used for identification by other features of the .NET Framework.</span></span>  
  
    - <span data-ttu-id="1d759-152">Задание свойства <xref:System.AppDomainSetup.ApplicationBase%2A> параметра `info` является обязательным для этой перегрузки.</span><span class="sxs-lookup"><span data-stu-id="1d759-152">Setting the <xref:System.AppDomainSetup.ApplicationBase%2A> property of the `info` parameter is mandatory for this overload.</span></span>  
  
    - <span data-ttu-id="1d759-153">Параметр `fullTrustAssemblies` имеет ключевое слово `params`, означающее, что создавать массив <xref:System.Security.Policy.StrongName> не обязательно.</span><span class="sxs-lookup"><span data-stu-id="1d759-153">The `fullTrustAssemblies` parameter has the `params` keyword, which means that it is not necessary to create a <xref:System.Security.Policy.StrongName> array.</span></span> <span data-ttu-id="1d759-154">Разрешается передавать в качестве параметров ноль, одно или несколько строгих имен.</span><span class="sxs-lookup"><span data-stu-id="1d759-154">Passing 0, 1, or more strong names as parameters is allowed.</span></span>  
  
    - <span data-ttu-id="1d759-155">Для создания домена приложения используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="1d759-155">The code to create the application domain is:</span></span>  
  
    ```csharp
    AppDomain newDomain = AppDomain.CreateDomain("Sandbox", null, adSetup, permSet, fullTrustAssembly);  
    ```  
  
5. <span data-ttu-id="1d759-156">Загрузите код в созданный ранее изолирующий домен <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="1d759-156">Load the code into the sandboxing <xref:System.AppDomain> that you created.</span></span> <span data-ttu-id="1d759-157">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="1d759-157">This can be done in two ways:</span></span>  
  
    - <span data-ttu-id="1d759-158">Вызовите для сборки метод <xref:System.AppDomain.ExecuteAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="1d759-158">Call the <xref:System.AppDomain.ExecuteAssembly%2A> method for the assembly.</span></span>  
  
    - <span data-ttu-id="1d759-159">Используйте метод <xref:System.Activator.CreateInstanceFrom%2A> для создания экземпляра класса, производного от <xref:System.MarshalByRefObject>, в новом домене <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="1d759-159">Use the <xref:System.Activator.CreateInstanceFrom%2A> method to create an instance of a class derived from <xref:System.MarshalByRefObject> in the new <xref:System.AppDomain>.</span></span>  
  
     <span data-ttu-id="1d759-160">Предпочтительнее использовать второй метод, так как в этом случае легче передавать параметры новому экземпляру домена <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="1d759-160">The second method is preferable, because it makes it easier to pass parameters to the new <xref:System.AppDomain> instance.</span></span> <span data-ttu-id="1d759-161">Метод <xref:System.Activator.CreateInstanceFrom%2A> предоставляет две важные возможности.</span><span class="sxs-lookup"><span data-stu-id="1d759-161">The <xref:System.Activator.CreateInstanceFrom%2A> method provides two important features:</span></span>  
  
    - <span data-ttu-id="1d759-162">Во-первых, можно использовать базу кода, указывающую на расположение, которое не содержит вашу сборку.</span><span class="sxs-lookup"><span data-stu-id="1d759-162">You can use a code base that points to a location that does not contain your assembly.</span></span>  
  
    - <span data-ttu-id="1d759-163">Во-вторых, при работе в режиме полного доверия (<xref:System.Security.CodeAccessPermission.Assert%2A>) можно использовать для создания экземпляра критически важного класса метод <xref:System.Security.Permissions.PermissionState.Unrestricted?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1d759-163">You can do the creation under an <xref:System.Security.CodeAccessPermission.Assert%2A> for full-trust (<xref:System.Security.Permissions.PermissionState.Unrestricted?displayProperty=nameWithType>), which enables you to create an instance of a critical class.</span></span> <span data-ttu-id="1d759-164">(Это происходит каждый раз, когда сборка не содержит метки прозрачности и загружается как полностью доверенная.) Поэтому необходимо быть осторожным при создании только кода, которому вы доверяете этой функции, и мы рекомендуем создавать только экземпляры полностью доверенных классов в новом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="1d759-164">(This happens whenever your assembly has no transparency markings and is loaded as fully trusted.) Therefore, you have to be careful to create only code that you trust with this function, and we recommend that you create only instances of fully trusted classes in the new application domain.</span></span>  
  
    ```csharp
    ObjectHandle handle = Activator.CreateInstanceFrom(  
    newDomain, typeof(Sandboxer).Assembly.ManifestModule.FullyQualifiedName,  
           typeof(Sandboxer).FullName );  
    ```  
  
     <span data-ttu-id="1d759-165">Чтобы создать экземпляр класса в новом домене, класс должен расширить <xref:System.MarshalByRefObject> класс.</span><span class="sxs-lookup"><span data-stu-id="1d759-165">To create an instance of a class in a new domain, the class must extend the <xref:System.MarshalByRefObject> class.</span></span>
  
    ```csharp
    class Sandboxer:MarshalByRefObject  
    ```  
  
6. <span data-ttu-id="1d759-166">Распакуйте новый экземпляр домена в ссылку в этом домене.</span><span class="sxs-lookup"><span data-stu-id="1d759-166">Unwrap the new domain instance into a reference in this domain.</span></span> <span data-ttu-id="1d759-167">Эта ссылка используется для выполнения ненадежного кода.</span><span class="sxs-lookup"><span data-stu-id="1d759-167">This reference is used to execute the untrusted code.</span></span>  
  
    ```csharp
    Sandboxer newDomainInstance = (Sandboxer) handle.Unwrap();  
    ```  
  
7. <span data-ttu-id="1d759-168">Вызовите метод `ExecuteUntrustedCode` в созданном экземпляре класса `Sandboxer`.</span><span class="sxs-lookup"><span data-stu-id="1d759-168">Call the `ExecuteUntrustedCode` method in the instance of the `Sandboxer` class you just created.</span></span>  
  
    ```csharp
    newDomainInstance.ExecuteUntrustedCode(untrustedAssembly, untrustedClass, entryPoint, parameters);  
    ```  
  
     <span data-ttu-id="1d759-169">Этот вызов выполняется в изолированном домене приложения, который имеет ограниченные разрешения.</span><span class="sxs-lookup"><span data-stu-id="1d759-169">This call is executed in the sandboxed application domain, which has restricted permissions.</span></span>  
  
    ```csharp
    public void ExecuteUntrustedCode(string assemblyName, string typeName, string entryPoint, Object[] parameters)  
    {  
        //Load the MethodInfo for a method in the new assembly. This might be a method you know, or
        //you can use Assembly.EntryPoint to get to the entry point in an executable.  
        MethodInfo target = Assembly.Load(assemblyName).GetType(typeName).GetMethod(entryPoint);  
        try  
        {  
            // Invoke the method.  
            target.Invoke(null, parameters);  
        }  
        catch (Exception ex)  
        {  
        //When information is obtained from a SecurityException extra information is provided if it is
        //accessed in full-trust.  
            new PermissionSet(PermissionState.Unrestricted).Assert();  
            Console.WriteLine("SecurityException caught:\n{0}", ex.ToString());  
            CodeAccessPermission.RevertAssert();  
            Console.ReadLine();  
        }  
    }  
    ```  
  
     <span data-ttu-id="1d759-170"><xref:System.Reflection> используется для получения дескриптора метода в сборке с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="1d759-170"><xref:System.Reflection> is used to get a handle of a method in the partially trusted assembly.</span></span> <span data-ttu-id="1d759-171">Этот дескриптор можно использовать для безопасного выполнения кода с минимальными разрешениями.</span><span class="sxs-lookup"><span data-stu-id="1d759-171">The handle can be used to execute code in a safe way with minimum permissions.</span></span>  
  
     <span data-ttu-id="1d759-172">В предыдущем коде обратите внимание на метод <xref:System.Security.PermissionSet.Assert%2A> для получения разрешения с полным доверием перед печатью <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="1d759-172">In the previous code, note the <xref:System.Security.PermissionSet.Assert%2A> for the full-trust permission before printing the <xref:System.Security.SecurityException>.</span></span>  
  
    ```csharp
    new PermissionSet(PermissionState.Unrestricted).Assert()  
    ```  
  
     <span data-ttu-id="1d759-173">Утверждение с полным доверием используется для получения расширенной информации из <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="1d759-173">The full-trust assert is used to obtain extended information from the <xref:System.Security.SecurityException>.</span></span> <span data-ttu-id="1d759-174">Если не используется утверждение <xref:System.Security.PermissionSet.Assert%2A>, метод <xref:System.Security.SecurityException.ToString%2A> исключения <xref:System.Security.SecurityException> обнаружит наличие в стеке кода с частичным доверием и ограничит возвращенные сведения.</span><span class="sxs-lookup"><span data-stu-id="1d759-174">Without the <xref:System.Security.PermissionSet.Assert%2A>, the <xref:System.Security.SecurityException.ToString%2A> method of <xref:System.Security.SecurityException> will discover that there is partially trusted code on the stack and will restrict the information returned.</span></span> <span data-ttu-id="1d759-175">Если бы код с частичным доверием мог считать эти сведения, создалась бы угроза безопасности. Во избежание этого разрешение <xref:System.Security.Permissions.UIPermission> не предоставляется.</span><span class="sxs-lookup"><span data-stu-id="1d759-175">This could cause security issues if the partial-trust code could read that information, but the risk is mitigated by not granting <xref:System.Security.Permissions.UIPermission>.</span></span> <span data-ttu-id="1d759-176">Утверждения полного доверия нужно использовать очень осторожно и только в том случае, если вы уверены, что уровень разрешений кода с частичным доверием не повысится до уровня полного доверия.</span><span class="sxs-lookup"><span data-stu-id="1d759-176">The full-trust assert should be used sparingly and only when you are sure that you are not allowing partial-trust code to elevate to full trust.</span></span> <span data-ttu-id="1d759-177">Как правило, не следует вызывать код без полного доверия в той же функции и после вызова утверждения полного доверия.</span><span class="sxs-lookup"><span data-stu-id="1d759-177">As a rule, do not call code you do not trust in the same function and after you called an assert for full trust.</span></span> <span data-ttu-id="1d759-178">Рекомендуется всегда отменять утверждение после завершения его использования.</span><span class="sxs-lookup"><span data-stu-id="1d759-178">It is good practice to always revert the assert when you have finished using it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d759-179">Пример</span><span class="sxs-lookup"><span data-stu-id="1d759-179">Example</span></span>  
 <span data-ttu-id="1d759-180">В примере ниже реализуется процедура, описанная в предыдущем подразделе.</span><span class="sxs-lookup"><span data-stu-id="1d759-180">The following example implements the procedure in the previous section.</span></span> <span data-ttu-id="1d759-181">В этом примере проект с именем `Sandboxer` в решении Visual Studio содержит проект с именем `UntrustedCode`, реализующий класс `UntrustedClass`.</span><span class="sxs-lookup"><span data-stu-id="1d759-181">In the example, a project named `Sandboxer` in a Visual Studio solution also contains a project named `UntrustedCode`, which implements the class `UntrustedClass`.</span></span> <span data-ttu-id="1d759-182">В этом сценарии предполагается, что загружена библиотечная сборка, содержащая метод, который должен вернуть значение `true` или `false`, указывающее, является ли предоставленное число числом Фибоначчи.</span><span class="sxs-lookup"><span data-stu-id="1d759-182">This scenario assumes that you have downloaded a library assembly containing a method that is expected to return `true` or `false` to indicate whether the number you provided is a Fibonacci number.</span></span> <span data-ttu-id="1d759-183">Вместо этого метод пытается считать файл с компьютера.</span><span class="sxs-lookup"><span data-stu-id="1d759-183">Instead, the method attempts to read a file from your computer.</span></span> <span data-ttu-id="1d759-184">В примере кода ниже показан ненадежный код.</span><span class="sxs-lookup"><span data-stu-id="1d759-184">The following example shows the untrusted code.</span></span>  
  
```csharp
using System;  
using System.IO;  
namespace UntrustedCode  
{  
    public class UntrustedClass  
    {  
        // Pretend to be a method checking if a number is a Fibonacci  
        // but which actually attempts to read a file.  
        public static bool IsFibonacci(int number)  
        {  
           File.ReadAllText("C:\\Temp\\file.txt");  
           return false;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="1d759-185">В примере ниже показан код приложения `Sandboxer`, выполняющий ненадежный код.</span><span class="sxs-lookup"><span data-stu-id="1d759-185">The following example shows the `Sandboxer` application code that executes the untrusted code.</span></span>  
  
```csharp
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.IO;  
using System.Security;  
using System.Security.Policy;  
using System.Security.Permissions;  
using System.Reflection;  
using System.Runtime.Remoting;  
  
//The Sandboxer class needs to derive from MarshalByRefObject so that we can create it in another
// AppDomain and refer to it from the default AppDomain.  
class Sandboxer : MarshalByRefObject  
{  
    const string pathToUntrusted = @"..\..\..\UntrustedCode\bin\Debug";  
    const string untrustedAssembly = "UntrustedCode";  
    const string untrustedClass = "UntrustedCode.UntrustedClass";  
    const string entryPoint = "IsFibonacci";  
    private static Object[] parameters = { 45 };  
    static void Main()  
    {  
        //Setting the AppDomainSetup. It is very important to set the ApplicationBase to a folder
        //other than the one in which the sandboxer resides.  
        AppDomainSetup adSetup = new AppDomainSetup();  
        adSetup.ApplicationBase = Path.GetFullPath(pathToUntrusted);  
  
        //Setting the permissions for the AppDomain. We give the permission to execute and to
        //read/discover the location where the untrusted code is loaded.  
        PermissionSet permSet = new PermissionSet(PermissionState.None);  
        permSet.AddPermission(new SecurityPermission(SecurityPermissionFlag.Execution));  
  
        //We want the sandboxer assembly's strong name, so that we can add it to the full trust list.  
        StrongName fullTrustAssembly = typeof(Sandboxer).Assembly.Evidence.GetHostEvidence<StrongName>();  
  
        //Now we have everything we need to create the AppDomain, so let's create it.  
        AppDomain newDomain = AppDomain.CreateDomain("Sandbox", null, adSetup, permSet, fullTrustAssembly);  
  
        //Use CreateInstanceFrom to load an instance of the Sandboxer class into the  
        //new AppDomain.
        ObjectHandle handle = Activator.CreateInstanceFrom(  
            newDomain, typeof(Sandboxer).Assembly.ManifestModule.FullyQualifiedName,  
            typeof(Sandboxer).FullName  
            );  
        //Unwrap the new domain instance into a reference in this domain and use it to execute the
        //untrusted code.  
        Sandboxer newDomainInstance = (Sandboxer) handle.Unwrap();  
        newDomainInstance.ExecuteUntrustedCode(untrustedAssembly, untrustedClass, entryPoint, parameters);  
    }  
    public void ExecuteUntrustedCode(string assemblyName, string typeName, string entryPoint, Object[] parameters)  
    {  
        //Load the MethodInfo for a method in the new Assembly. This might be a method you know, or
        //you can use Assembly.EntryPoint to get to the main function in an executable.  
        MethodInfo target = Assembly.Load(assemblyName).GetType(typeName).GetMethod(entryPoint);  
        try  
        {  
            //Now invoke the method.  
            bool retVal = (bool)target.Invoke(null, parameters);  
        }  
        catch (Exception ex)  
        {  
            // When we print informations from a SecurityException extra information can be printed if we are
            //calling it with a full-trust stack.  
            new PermissionSet(PermissionState.Unrestricted).Assert();  
            Console.WriteLine("SecurityException caught:\n{0}", ex.ToString());  
            CodeAccessPermission.RevertAssert();  
            Console.ReadLine();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1d759-186">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1d759-186">See also</span></span>

- [<span data-ttu-id="1d759-187">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="1d759-187">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
