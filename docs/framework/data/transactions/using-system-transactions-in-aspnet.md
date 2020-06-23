---
title: Использование инфраструктуры System.Transactions в среде ASP.NET
description: Используйте System. Transactions внутри приложения ASP.NET. Включить разрешения распределенных транзакций и работать с динамической компиляцией.
ms.date: 03/30/2017
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
ms.openlocfilehash: 48907faf99953e34d045a1e0d79eed8a788187b5
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141648"
---
# <a name="using-systemtransactions-in-aspnet"></a><span data-ttu-id="d2016-104">Использование инфраструктуры System.Transactions в среде ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d2016-104">Using System.Transactions in ASP.NET</span></span>
<span data-ttu-id="d2016-105">В этом разделе описывается, как можно успешно использовать инфраструктуру <xref:System.Transactions> в приложении ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d2016-105">This topic describes how you can successfully use <xref:System.Transactions> inside an ASP.NET application.</span></span>

## <a name="enable-distributedtransactionpermission-in-aspnet"></a><span data-ttu-id="d2016-106">Включение разрешения DistributedTransactionPermission в ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d2016-106">Enable DistributedTransactionPermission in ASP.NET</span></span>
 <span data-ttu-id="d2016-107"><xref:System.Transactions>поддерживает частично доверенные вызывающие объекты и помечается `AllowPartiallyTrustedCallers` атрибутом (APTCA).</span><span class="sxs-lookup"><span data-stu-id="d2016-107"><xref:System.Transactions> supports partially trusted callers and is marked with the `AllowPartiallyTrustedCallers` attribute (APTCA).</span></span> <span data-ttu-id="d2016-108">Уровни доверия для определяются на <xref:System.Transactions> основе типов ресурсов (например, системной памяти, общих ресурсов для всего процесса, системных ресурсов и других ресурсов), которые <xref:System.Transactions> предоставляют и уровень доверия, который должен быть необходим для доступа к этим ресурсам.</span><span class="sxs-lookup"><span data-stu-id="d2016-108">The trust levels for <xref:System.Transactions> are defined based on the types of resources (for example, system memory, shared process-wide resources, system-wide resources, and other resources) that <xref:System.Transactions> exposes and the level of trust that should be required to access those resources.</span></span> <span data-ttu-id="d2016-109">В среде с частичным доверием сборка с неполным доверием может использовать только транзакции внутри домена приложения (в этом случае единственным защищаемым ресурсом является системная память), пока этой сборке не будет предоставлено разрешение <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="d2016-109">In a partial-trust environment, a non-full trust assembly can only use transactions within the Application Domain (in this case, the only resource being protected is system memory), unless it is granted the <xref:System.Transactions.DistributedTransactionPermission>.</span></span>

 <span data-ttu-id="d2016-110">Разрешение<xref:System.Transactions.DistributedTransactionPermission> запрашивается при каждой передаче управления транзакцией координатору распределенных транзакций (Майкрософт) (MSDTC).</span><span class="sxs-lookup"><span data-stu-id="d2016-110"><xref:System.Transactions.DistributedTransactionPermission> is demanded whenever transaction management is escalated to be managed by the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span> <span data-ttu-id="d2016-111">В этом сценарии используются ресурсы, общие для всего процесса, и прежде всего один глобальный ресурс, зарезервированный в журнале MSDTC,</span><span class="sxs-lookup"><span data-stu-id="d2016-111">This kind of scenario utilizes process-wide resources and particularly a global resource, which is the reserved space in the MSDTC log.</span></span> <span data-ttu-id="d2016-112">например внешнее веб-приложение для взаимодействия с базой данных или приложение, использующее базу данных в рамках предоставляемых им служб.</span><span class="sxs-lookup"><span data-stu-id="d2016-112">An example of this usage is a Web front-end to a database or an application that uses a database as part of the services it provides.</span></span>

 <span data-ttu-id="d2016-113">У среды ASP.NET имеется собственный набор уровней доверия, с которыми с помощью файлов политики связан определенный набор разрешений.</span><span class="sxs-lookup"><span data-stu-id="d2016-113">ASP.NET has its own set of trust levels and associates a specific set of permissions with these trust levels through policy files.</span></span> <span data-ttu-id="d2016-114">Дополнительные сведения см. в разделе [ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d2016-114">For more information, see [ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100)).</span></span> <span data-ttu-id="d2016-115">При первоначальной установке Windows SDK ни один из файлов политики ASP.NET по умолчанию не связан с <xref:System.Transactions.DistributedTransactionPermission> .</span><span class="sxs-lookup"><span data-stu-id="d2016-115">When you initially install the Windows SDK, none of the default ASP.NET policy files are associated with the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="d2016-116">Поэтому передачу управления транзакцией приложения ASP.NET координатору MSDTC выполнить не удается — возникает исключение <xref:System.Security.SecurityException> при запросе разрешения <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="d2016-116">As such, when your transaction in an ASP.NET application is escalated to be managed by the MSDTC, the escalation fails with a <xref:System.Security.SecurityException> upon demanding the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="d2016-117">Чтобы обеспечить передачу транзакции на следующий уровень иерархии среды ASP.NET с частичным доверием, необходимо предоставить разрешение <xref:System.Transactions.DistributedTransactionPermission> для уровней доверия по умолчанию, у которых есть разрешение <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="d2016-117">To enable transaction escalation in an ASP.NET partial trust environment, you should grant the <xref:System.Transactions.DistributedTransactionPermission> in the same default trust levels as those of <xref:System.Data.SqlClient.SqlClientPermission>.</span></span> <span data-ttu-id="d2016-118">Можно настроить пользовательский уровень доверия и файл политики для его поддержки или изменить файлы политики по умолчанию **Web_hightrust.config** и **Web_mediumtrust.config**.</span><span class="sxs-lookup"><span data-stu-id="d2016-118">You can either configure your own custom trust level and policy file to support this, or you can modify the default policy files, which are **Web_hightrust.config** and **Web_mediumtrust.config**.</span></span>

 <span data-ttu-id="d2016-119">Чтобы изменить файлы политики, добавьте `SecurityClass` элемент для `DistributedTransactionPermission` в `SecurityClasses` элемент в `PolicyLevel` элементе и добавьте соответствующий `IPermission` элемент в ASP.NET `NamedPermissionSet` для System. Transactions.</span><span class="sxs-lookup"><span data-stu-id="d2016-119">To modify the policy files, add a `SecurityClass` element for `DistributedTransactionPermission` to the `SecurityClasses` element under the `PolicyLevel` element and add a corresponding `IPermission` element under the ASP.NET `NamedPermissionSet` for System.Transactions.</span></span> <span data-ttu-id="d2016-120">Это показано в следующем файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2016-120">The following configuration file demonstrates this.</span></span>

```xml
<SecurityClasses>
   <SecurityClass Name="DistributedTransactionPermission" Description="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
...
</SecurityClasses>

<PermissionSet
  class="NamedPermissionSet"
  version="1"
  Name="ASP.Net">
     <IPermission
        class="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
        version="1"
        Unrestricted="true"
     />
...
</PermissionSet>
```

 <span data-ttu-id="d2016-121">Дополнительные сведения о политике безопасности ASP.NET см. в разделе [элемент SecurityPolicy (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d2016-121">For more information about ASP.NET security policy, see [securityPolicy Element (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100)).</span></span>

## <a name="dynamic-compilation"></a><span data-ttu-id="d2016-122">Динамическая компиляция</span><span class="sxs-lookup"><span data-stu-id="d2016-122">Dynamic Compilation</span></span>
 <span data-ttu-id="d2016-123">Чтобы импортировать и использовать <xref:System.Transactions> в приложении ASP.NET, динамически компилируемом во время доступа, в файле конфигурации необходимо указать ссылку на сборку <xref:System.Transactions>.</span><span class="sxs-lookup"><span data-stu-id="d2016-123">If you want to import and use <xref:System.Transactions> in an ASP.NET application that is dynamically compiled on access, you should place a reference to the <xref:System.Transactions> assembly in the configuration file.</span></span> <span data-ttu-id="d2016-124">В частности, ссылка должна добавляться в `compilation/assemblies` раздел корневого **Web.config** по умолчанию файла конфигурации или конкретного файла конфигурации веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="d2016-124">Specifically, the reference should be added under the `compilation/assemblies` section of the default root **Web.config** configuration file, or a specific Web application's configuration file.</span></span> <span data-ttu-id="d2016-125">Это продемонстрировано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d2016-125">The following example demonstrates this.</span></span>

```xml
<configuration>
   <system.web>
      <compilation>
         <assemblies>
      <add assembly="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
         </assemblies>
      </compilation>
   </system.web>
</configuration>
```

 <span data-ttu-id="d2016-126">Дополнительные сведения см. в разделе [Добавление элемента для сборок для компиляции (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d2016-126">For more information, see [add Element for assemblies for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100)).</span></span>

## <a name="see-also"></a><span data-ttu-id="d2016-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d2016-127">See also</span></span>

- <span data-ttu-id="d2016-128">[ASP.NET уровни доверия и файлы политик](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d2016-128">[ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))</span></span>
- <span data-ttu-id="d2016-129">[Элемент securityPolicy (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d2016-129">[securityPolicy Element (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))</span></span>
- [<span data-ttu-id="d2016-130">Передача управления транзакцией на следующий уровень иерархии</span><span class="sxs-lookup"><span data-stu-id="d2016-130">Transaction Management Escalation</span></span>](transaction-management-escalation.md)
