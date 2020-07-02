---
ms.openlocfilehash: 809ca85b347fabc44573e2e0c5a43261d68590d3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621251"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a><span data-ttu-id="e930d-101">Функция сохраняемости SQL для рабочего процесса добавляет кластеры первичных ключей и не допускает значения NULL в некоторых столбцах</span><span class="sxs-lookup"><span data-stu-id="e930d-101">Workflow SQL persistence adds primary key clusters and disallows null values in some columns</span></span>

#### <a name="details"></a><span data-ttu-id="e930d-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="e930d-102">Details</span></span>

<span data-ttu-id="e930d-103">Начиная с версии .NET Framework 4.7, таблицы, созданные для хранилища экземпляров рабочего процесса SQL (SWIS) с помощью скрипта SqlWorkflowInstanceStoreSchema.sql, используют кластеризованные первичные ключи.</span><span class="sxs-lookup"><span data-stu-id="e930d-103">Starting with the .NET Framework 4.7, the tables created for the SQL Workflow Instance Store (SWIS) by the SqlWorkflowInstanceStoreSchema.sql script use clustered primary keys.</span></span> <span data-ttu-id="e930d-104">Из-за этого удостоверения не поддерживают значения <code>null</code>.</span><span class="sxs-lookup"><span data-stu-id="e930d-104">Because of this, identities do not support <code>null</code> values.</span></span> <span data-ttu-id="e930d-105">Это изменение не влияет на работу SWIS.</span><span class="sxs-lookup"><span data-stu-id="e930d-105">The operation of SWIS is not impacted by this change.</span></span> <span data-ttu-id="e930d-106">Были внесены обновления в поддержку механизма репликации транзакций SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e930d-106">The updates were made to support SQL Server Transactional Replication.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e930d-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="e930d-107">Suggestion</span></span>

<span data-ttu-id="e930d-108">Чтобы реализовать это изменение, в существующую установку необходимо добавить SQL-файл SqlWorkflowInstanceStoreSchemaUpgrade.sql.</span><span class="sxs-lookup"><span data-stu-id="e930d-108">The SQL file SqlWorkflowInstanceStoreSchemaUpgrade.sql must be applied to existing installations in order to experience this change.</span></span> <span data-ttu-id="e930d-109">В новых установках баз данных это изменение реализуется автоматически.</span><span class="sxs-lookup"><span data-stu-id="e930d-109">New database installations will automatically have the change.</span></span>

| <span data-ttu-id="e930d-110">name</span><span class="sxs-lookup"><span data-stu-id="e930d-110">Name</span></span>    | <span data-ttu-id="e930d-111">Значение</span><span class="sxs-lookup"><span data-stu-id="e930d-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e930d-112">Область</span><span class="sxs-lookup"><span data-stu-id="e930d-112">Scope</span></span>   |<span data-ttu-id="e930d-113">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="e930d-113">Edge</span></span>|
|<span data-ttu-id="e930d-114">Version</span><span class="sxs-lookup"><span data-stu-id="e930d-114">Version</span></span>|<span data-ttu-id="e930d-115">4.7</span><span class="sxs-lookup"><span data-stu-id="e930d-115">4.7</span></span>|
|<span data-ttu-id="e930d-116">Type</span><span class="sxs-lookup"><span data-stu-id="e930d-116">Type</span></span>|<span data-ttu-id="e930d-117">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="e930d-117">Runtime</span></span>|
