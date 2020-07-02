---
ms.openlocfilehash: 687118157020ede200f97a0125c4740a06bf4b5e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620613"
---
### <a name="different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>Исключения обрабатываются по-разному для методов ObjectContext.CreateDatabase и DbProviderServices.CreateDatabase

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.5, если происходит сбой создания базы данных, методы <code>CreateDatabase</code> будут пытаться удалить пустую базу данных. Если эта операция выполняется успешно, будет распространяться исходное исключение <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> (вместо <xref:System.InvalidOperationException?displayProperty=fullName>, которое всегда создавалось в .NET Framework 4.0).

#### <a name="suggestion"></a>Предложение

При перехвате <xref:System.InvalidOperationException?displayProperty=fullName> во время выполнения <xref:System.Data.Objects.ObjectContext.CreateDatabase> или <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)> теперь также должны обрабатываться исключения SQLException.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType></li></ul>|
