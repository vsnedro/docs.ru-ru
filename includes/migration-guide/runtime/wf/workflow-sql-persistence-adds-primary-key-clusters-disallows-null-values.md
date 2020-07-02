---
ms.openlocfilehash: 809ca85b347fabc44573e2e0c5a43261d68590d3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621251"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a>Функция сохраняемости SQL для рабочего процесса добавляет кластеры первичных ключей и не допускает значения NULL в некоторых столбцах

#### <a name="details"></a>Подробнее

Начиная с версии .NET Framework 4.7, таблицы, созданные для хранилища экземпляров рабочего процесса SQL (SWIS) с помощью скрипта SqlWorkflowInstanceStoreSchema.sql, используют кластеризованные первичные ключи. Из-за этого удостоверения не поддерживают значения <code>null</code>. Это изменение не влияет на работу SWIS. Были внесены обновления в поддержку механизма репликации транзакций SQL Server.

#### <a name="suggestion"></a>Предложение

Чтобы реализовать это изменение, в существующую установку необходимо добавить SQL-файл SqlWorkflowInstanceStoreSchemaUpgrade.sql. В новых установках баз данных это изменение реализуется автоматически.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.7|
|Type|Среда выполнения|
