---
ms.openlocfilehash: 241184d61d718fedfea396260e739d2dbc05c305
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620601"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a>SqlConnection больше не может подключаться к SQL Server 1997 или базам данных с помощью адаптера VIA

#### <a name="details"></a>Подробнее

Подключения к базам данных SQL Server с помощью [протокола Virtual Interface Adapter (VIA)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) больше не поддерживаются. Протокол, используемый для подключения к базе данных SQL Server, отображается в строке подключения. Для соединения VIA указано via:&lt;имя_сервера&gt;. Если это приложение подключается к SQL по протоколу, который отличается от VIA (например, tcp: или np:), критических изменений не будет. Также больше не поддерживаются подключения к SQL Server 7 (1997).

#### <a name="suggestion"></a>Предложение

Не рекомендуется использовать протокол VIA. Выберите другой протокол для подключения к базам данных SQL. Обычно используется протокол TCP/IP. Дополнительные сведения см. в статье [Практическое руководство. Включение протокола TCP/IP для экземпляра базы данных](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)). Если доступ к базе данных осуществляется только из интрасети, протокол общих каналов может обеспечить более высокую производительность, если сеть работает слишком медленно.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)></li></ul>|
