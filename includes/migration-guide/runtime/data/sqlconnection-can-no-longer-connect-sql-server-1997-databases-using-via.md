---
ms.openlocfilehash: e65ba0edb132f5cded244a69d58e43ffea76a039
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606902"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a>SqlConnection больше не может подключаться к SQL Server 1997 или базам данных с помощью адаптера VIA

#### <a name="details"></a>Подробнее

Подключения к базам данных SQL Server с помощью [протокола Virtual Interface Adapter (VIA)](/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) больше не поддерживаются. Протокол, используемый для подключения к базе данных SQL Server, отображается в строке подключения. Для соединения VIA указано via:&lt;имя_сервера&gt;. Если это приложение подключается к SQL по протоколу, который отличается от VIA (например, tcp: или np:), критических изменений не будет. Также больше не поддерживаются подключения к SQL Server 7 (1997).

#### <a name="suggestion"></a>Предложение

Не рекомендуется использовать протокол VIA. Выберите другой протокол для подключения к базам данных SQL. Обычно используется протокол TCP/IP. Дополнительные сведения см. в статье [Практическое руководство. Включение протокола TCP/IP для экземпляра базы данных](/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)). Если доступ к базе данных осуществляется только из интрасети, протокол общих каналов может обеспечить более высокую производительность, если сеть работает слишком медленно.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)>
- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)>

<!--

#### Affected APIs

- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String)`
- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String,System.Data.SqlClient.SqlCredential)`

-->
