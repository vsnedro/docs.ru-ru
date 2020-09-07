---
ms.openlocfilehash: 8c593fa6490451c6236f0d4390f09d4e9e4f0cbb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497802"
---
### <a name="different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a><span data-ttu-id="e7ad0-101">Исключения обрабатываются по-разному для методов ObjectContext.CreateDatabase и DbProviderServices.CreateDatabase</span><span class="sxs-lookup"><span data-stu-id="e7ad0-101">Different exception handling for ObjectContext.CreateDatabase and DbProviderServices.CreateDatabase methods</span></span>

#### <a name="details"></a><span data-ttu-id="e7ad0-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="e7ad0-102">Details</span></span>

<span data-ttu-id="e7ad0-103">Начиная с .NET Framework 4.5, если происходит сбой создания базы данных, методы <code>CreateDatabase</code> будут пытаться удалить пустую базу данных.</span><span class="sxs-lookup"><span data-stu-id="e7ad0-103">Beginning in .NET Framework 4.5, if database creation fails, <code>CreateDatabase</code> methods will attempt to drop the empty database.</span></span> <span data-ttu-id="e7ad0-104">Если эта операция выполняется успешно, будет распространяться исходное исключение <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> (вместо <xref:System.InvalidOperationException?displayProperty=fullName>, которое всегда создавалось в .NET Framework 4.0).</span><span class="sxs-lookup"><span data-stu-id="e7ad0-104">If that operation succeeds, the original <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> will be propagated (instead of the <xref:System.InvalidOperationException?displayProperty=fullName> that was always thrown in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e7ad0-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="e7ad0-105">Suggestion</span></span>

<span data-ttu-id="e7ad0-106">При перехвате <xref:System.InvalidOperationException?displayProperty=fullName> во время выполнения <xref:System.Data.Objects.ObjectContext.CreateDatabase> или <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)> теперь также должны обрабатываться исключения SQLException.</span><span class="sxs-lookup"><span data-stu-id="e7ad0-106">When catching an <xref:System.InvalidOperationException?displayProperty=fullName> while executing <xref:System.Data.Objects.ObjectContext.CreateDatabase> or <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)>, SQLExceptions should now also be caught.</span></span>

| <span data-ttu-id="e7ad0-107">name</span><span class="sxs-lookup"><span data-stu-id="e7ad0-107">Name</span></span>    | <span data-ttu-id="e7ad0-108">Значение</span><span class="sxs-lookup"><span data-stu-id="e7ad0-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e7ad0-109">Область</span><span class="sxs-lookup"><span data-stu-id="e7ad0-109">Scope</span></span>   |<span data-ttu-id="e7ad0-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="e7ad0-110">Minor</span></span>|
|<span data-ttu-id="e7ad0-111">Version</span><span class="sxs-lookup"><span data-stu-id="e7ad0-111">Version</span></span>|<span data-ttu-id="e7ad0-112">4.5</span><span class="sxs-lookup"><span data-stu-id="e7ad0-112">4.5</span></span>|
|<span data-ttu-id="e7ad0-113">Type</span><span class="sxs-lookup"><span data-stu-id="e7ad0-113">Type</span></span>|<span data-ttu-id="e7ad0-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="e7ad0-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="e7ad0-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="e7ad0-115">Affected APIs</span></span>

- <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType>
- <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Data.Objects.ObjectContext.CreateDatabase`
- `M:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)`

-->
