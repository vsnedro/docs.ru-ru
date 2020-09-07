---
ms.openlocfilehash: cb9305f623044233082286863d2f2d2c7e9d665a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497235"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a>Функция сохраняемости SQL для рабочего процесса добавляет кластеры первичных ключей и не допускает значения NULL в некоторых столбцах

#### <a name="details"></a>Подробнее

Начиная с версии .NET Framework 4.7, таблицы, созданные для хранилища экземпляров рабочего процесса SQL (SWIS) с помощью скрипта SqlWorkflowInstanceStoreSchema.sql, используют кластеризованные первичные ключи. Из-за этого удостоверения не поддерживают значения <code>null</code>. Это изменение не влияет на работу SWIS. Были внесены обновления в поддержку механизма репликации транзакций SQL Server.

#### <a name="suggestion"></a>Предложение

Чтобы реализовать это изменение, в существующую установку необходимо добавить SQL-файл SqlWorkflowInstanceStoreSchemaUpgrade.sql. В новых установках баз данных это изменение реализуется автоматически.

| Имя    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.7|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
