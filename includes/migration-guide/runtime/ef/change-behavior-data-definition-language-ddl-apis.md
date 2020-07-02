---
ms.openlocfilehash: 4396ff43a48a23df29c5938b6bd2137d527b4ef5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620612"
---
### <a name="change-in-behavior-in-data-definition-language-ddl-apis"></a>Изменение поведения API-интерфейсов языка описания данных (DDL)

#### <a name="details"></a>Подробнее

Поведение API-интерфейсов языка DDL при заданном значении AttachDBFilename изменилось следующим образом.<ul><li>В строках подключения не требуется указывать значение Initial Catalog. Ранее требовались оба значения — AttachDBFilename и Initial Catalog.</li><li>Если указаны AttachDBFilename и Initial Catalog и данный MDF-файл существует, метод <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A> возвращает значение <code>true</code>. Раньше он возвращал значение <code>false</code>.</li><li>Если указаны AttachDBFilename и Initial Catalog и данный MDF-файл существует, при вызове метода <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A> файлы будут удалены.</li><li>При вызове метода <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>, когда в строке подключения указано значение AttachDBFilename с несуществующим MDF-файлом и Initial Catalog не существует, этот метод вызывает исключение <xref:System.InvalidOperationException>. Раньше он вызывал исключение <xref:System.Data.SqlClient.SqlException>.</li></ul>

#### <a name="suggestion"></a>Предложение

Эти изменения облегчают создание средств и приложений, в которых используются API-интерфейсы DDL. Эти изменения могут повлиять на совместимость приложений в следующих сценариях:<ul><li>Пользователь пишет код, который выполняет команду <code>DROP DATABASE</code> напрямую, а не вызывает метод <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>, если метод <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A> возвращает значение <code>true</code>. Это нарушает логику существующего кода, если база данных не присоединена, но MDF-файл существует.</li><li>Пользователь пишет код, который ожидает, что метод <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A> вызовет исключение <xref:System.Data.SqlClient.SqlException>, а не <xref:System.InvalidOperationException>, когда Initial Catalog и MDF-файл не существуют.</li></ul>

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5|
|Type|Среда выполнения|
