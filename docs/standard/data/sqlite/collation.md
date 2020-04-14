---
title: Параметры сортировки
ms.date: 12/13/2019
description: Узнайте, как создать пользовательскую последовательность сопоставления.
ms.openlocfilehash: 9879846cc191a62c4cb47a0fbaa47c59153ba61c
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242976"
---
# <a name="collation"></a><span data-ttu-id="46cb7-103">Параметры сортировки</span><span class="sxs-lookup"><span data-stu-id="46cb7-103">Collation</span></span>

<span data-ttu-id="46cb7-104">Коллаизирование последовательностей используется S'Lite при сравнении значений TEXT для определения порядка и равенства.</span><span class="sxs-lookup"><span data-stu-id="46cb7-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="46cb7-105">Можно указать, какой коллаж использовать при создании столбцов или на операцию в запросах S'L.</span><span class="sxs-lookup"><span data-stu-id="46cb7-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="46cb7-106">По умолчанию S'Lite включает в себя три последовательности коллажа.</span><span class="sxs-lookup"><span data-stu-id="46cb7-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="46cb7-107">Параметры сортировки</span><span class="sxs-lookup"><span data-stu-id="46cb7-107">Collation</span></span> | <span data-ttu-id="46cb7-108">Описание</span><span class="sxs-lookup"><span data-stu-id="46cb7-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="46cb7-109">RTRIM</span><span class="sxs-lookup"><span data-stu-id="46cb7-109">RTRIM</span></span>     | <span data-ttu-id="46cb7-110">Игнорирует задняя белая область</span><span class="sxs-lookup"><span data-stu-id="46cb7-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="46cb7-111">НОКЕЙС</span><span class="sxs-lookup"><span data-stu-id="46cb7-111">NOCASE</span></span>    | <span data-ttu-id="46cb7-112">Нечувствительные к делу для символов ASCII А-Я</span><span class="sxs-lookup"><span data-stu-id="46cb7-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="46cb7-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="46cb7-113">BINARY</span></span>    | <span data-ttu-id="46cb7-114">Дело чувствительное.</span><span class="sxs-lookup"><span data-stu-id="46cb7-114">Case-sensitive.</span></span> <span data-ttu-id="46cb7-115">Сравнивает байты напрямую</span><span class="sxs-lookup"><span data-stu-id="46cb7-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="46cb7-116">Пользовательский коллаж</span><span class="sxs-lookup"><span data-stu-id="46cb7-116">Custom collation</span></span>

<span data-ttu-id="46cb7-117">Вы также можете определить свои собственные последовательности сопоставления <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>или переопределить встроенные с помощью.</span><span class="sxs-lookup"><span data-stu-id="46cb7-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="46cb7-118">Ниже приводится следующий пример, переопределяемый коллаж NOCASE для поддержки символов Unicode.</span><span class="sxs-lookup"><span data-stu-id="46cb7-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="46cb7-119">[Полный пример кода](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) доступен на GitHub.</span><span class="sxs-lookup"><span data-stu-id="46cb7-119">The [full sample code](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="46cb7-120">Like - оператор</span><span class="sxs-lookup"><span data-stu-id="46cb7-120">Like operator</span></span>

<span data-ttu-id="46cb7-121">Оператор LIKE в S'Lite не соблюдает коллажа.</span><span class="sxs-lookup"><span data-stu-id="46cb7-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="46cb7-122">Реализация по умолчанию имеет ту же семантику, что и коллаж NOCASE.</span><span class="sxs-lookup"><span data-stu-id="46cb7-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="46cb7-123">Это только случай бесчувственным для ASCII символов а через Я.</span><span class="sxs-lookup"><span data-stu-id="46cb7-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="46cb7-124">Вы можете легко сделать оператора LIKE чувствительным, используя следующее заявление прагмы:</span><span class="sxs-lookup"><span data-stu-id="46cb7-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 1
```

<span data-ttu-id="46cb7-125">Подробнее о выполнении оператора LIKE читайте в материале [«Функции,](user-defined-functions.md) определяемые пользователями».</span><span class="sxs-lookup"><span data-stu-id="46cb7-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="46cb7-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="46cb7-126">See also</span></span>

* [<span data-ttu-id="46cb7-127">Определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="46cb7-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="46cb7-128">Синтаксис СЗЛ</span><span class="sxs-lookup"><span data-stu-id="46cb7-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
