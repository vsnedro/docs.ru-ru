---
ms.openlocfilehash: cb9305f623044233082286863d2f2d2c7e9d665a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497235"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a><span data-ttu-id="186c2-101">Функция сохраняемости SQL для рабочего процесса добавляет кластеры первичных ключей и не допускает значения NULL в некоторых столбцах</span><span class="sxs-lookup"><span data-stu-id="186c2-101">Workflow SQL persistence adds primary key clusters and disallows null values in some columns</span></span>

#### <a name="details"></a><span data-ttu-id="186c2-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="186c2-102">Details</span></span>

<span data-ttu-id="186c2-103">Начиная с версии .NET Framework 4.7, таблицы, созданные для хранилища экземпляров рабочего процесса SQL (SWIS) с помощью скрипта SqlWorkflowInstanceStoreSchema.sql, используют кластеризованные первичные ключи.</span><span class="sxs-lookup"><span data-stu-id="186c2-103">Starting with the .NET Framework 4.7, the tables created for the SQL Workflow Instance Store (SWIS) by the SqlWorkflowInstanceStoreSchema.sql script use clustered primary keys.</span></span> <span data-ttu-id="186c2-104">Из-за этого удостоверения не поддерживают значения <code>null</code>.</span><span class="sxs-lookup"><span data-stu-id="186c2-104">Because of this, identities do not support <code>null</code> values.</span></span> <span data-ttu-id="186c2-105">Это изменение не влияет на работу SWIS.</span><span class="sxs-lookup"><span data-stu-id="186c2-105">The operation of SWIS is not impacted by this change.</span></span> <span data-ttu-id="186c2-106">Были внесены обновления в поддержку механизма репликации транзакций SQL Server.</span><span class="sxs-lookup"><span data-stu-id="186c2-106">The updates were made to support SQL Server Transactional Replication.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="186c2-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="186c2-107">Suggestion</span></span>

<span data-ttu-id="186c2-108">Чтобы реализовать это изменение, в существующую установку необходимо добавить SQL-файл SqlWorkflowInstanceStoreSchemaUpgrade.sql.</span><span class="sxs-lookup"><span data-stu-id="186c2-108">The SQL file SqlWorkflowInstanceStoreSchemaUpgrade.sql must be applied to existing installations in order to experience this change.</span></span> <span data-ttu-id="186c2-109">В новых установках баз данных это изменение реализуется автоматически.</span><span class="sxs-lookup"><span data-stu-id="186c2-109">New database installations will automatically have the change.</span></span>

| <span data-ttu-id="186c2-110">Имя</span><span class="sxs-lookup"><span data-stu-id="186c2-110">Name</span></span>    | <span data-ttu-id="186c2-111">Значение</span><span class="sxs-lookup"><span data-stu-id="186c2-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="186c2-112">Область</span><span class="sxs-lookup"><span data-stu-id="186c2-112">Scope</span></span>   |<span data-ttu-id="186c2-113">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="186c2-113">Edge</span></span>|
|<span data-ttu-id="186c2-114">Version</span><span class="sxs-lookup"><span data-stu-id="186c2-114">Version</span></span>|<span data-ttu-id="186c2-115">4.7</span><span class="sxs-lookup"><span data-stu-id="186c2-115">4.7</span></span>|
|<span data-ttu-id="186c2-116">Type</span><span class="sxs-lookup"><span data-stu-id="186c2-116">Type</span></span>|<span data-ttu-id="186c2-117">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="186c2-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="186c2-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="186c2-118">Affected APIs</span></span>

<span data-ttu-id="186c2-119">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="186c2-119">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
