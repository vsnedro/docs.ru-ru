---
title: Строки подключения
ms.date: 12/13/2019
description: Поддерживаемые ключевые слова и значения строк подключения.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401199"
---
# <a name="connection-strings"></a><span data-ttu-id="b358d-103">Строки подключения</span><span class="sxs-lookup"><span data-stu-id="b358d-103">Connection strings</span></span>

<span data-ttu-id="b358d-104">Строка подключения используется для определения способа подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="b358d-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="b358d-105">В Microsoft.Data.Sqlite используется стандартный [синтаксис ADO.NET](../../../framework/data/adonet/connection-strings.md) строк подключения — список пар ключевых слов и значений, разделенных точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="b358d-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="b358d-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="b358d-106">Keywords</span></span>

<span data-ttu-id="b358d-107">Microsoft.Data.Sqlite позволяет использовать следующие ключевые слова в строке подключения:</span><span class="sxs-lookup"><span data-stu-id="b358d-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="b358d-108">Источник данных</span><span class="sxs-lookup"><span data-stu-id="b358d-108">Data source</span></span>

<span data-ttu-id="b358d-109">Путь к файлу базы данных.</span><span class="sxs-lookup"><span data-stu-id="b358d-109">The path to the database file.</span></span> <span data-ttu-id="b358d-110">*DataSource* (без пробела) и *Filename* — псевдонимы этого ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="b358d-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="b358d-111">SQLite обрабатывает относительные пути к текущей рабочей папке.</span><span class="sxs-lookup"><span data-stu-id="b358d-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="b358d-112">Можно также указать абсолютные пути.</span><span class="sxs-lookup"><span data-stu-id="b358d-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="b358d-113">Если **ничего не указано**, SQLite создает временную базу данных на диске, которая удаляется при закрытии соединения.</span><span class="sxs-lookup"><span data-stu-id="b358d-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="b358d-114">Если указано `:memory:`, используется выполняющаяся в памяти база данных.</span><span class="sxs-lookup"><span data-stu-id="b358d-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="b358d-115">См. сведения о [выполняющихся в памяти базах данных](in-memory-databases.md).</span><span class="sxs-lookup"><span data-stu-id="b358d-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="b358d-116">Пути, начинающиеся со строки подстановки `|DataDirectory|`, обрабатываются так же, как и относительные пути.</span><span class="sxs-lookup"><span data-stu-id="b358d-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="b358d-117">Если пути указаны, они становятся относительными для значения свойства домена приложения DataDirectory.</span><span class="sxs-lookup"><span data-stu-id="b358d-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="b358d-118">Это ключевое слово также поддерживает [имена файлов в формате URI](https://www.sqlite.org/uri.html).</span><span class="sxs-lookup"><span data-stu-id="b358d-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="b358d-119">Режим</span><span class="sxs-lookup"><span data-stu-id="b358d-119">Mode</span></span>

<span data-ttu-id="b358d-120">Режим подключения.</span><span class="sxs-lookup"><span data-stu-id="b358d-120">The connection mode.</span></span>

| <span data-ttu-id="b358d-121">Значение</span><span class="sxs-lookup"><span data-stu-id="b358d-121">Value</span></span>           | <span data-ttu-id="b358d-122">Описание</span><span class="sxs-lookup"><span data-stu-id="b358d-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="b358d-123">ReadWriteCreate</span><span class="sxs-lookup"><span data-stu-id="b358d-123">ReadWriteCreate</span></span> | <span data-ttu-id="b358d-124">Открывает базу данных для чтения и записи, а также создает ее, если она не существует.</span><span class="sxs-lookup"><span data-stu-id="b358d-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="b358d-125">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b358d-125">This is the default.</span></span> |
| <span data-ttu-id="b358d-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b358d-126">ReadWrite</span></span>       | <span data-ttu-id="b358d-127">Открывает базу данных для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="b358d-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="b358d-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="b358d-128">ReadOnly</span></span>        | <span data-ttu-id="b358d-129">Открывает базу данных только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b358d-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="b358d-130">Память</span><span class="sxs-lookup"><span data-stu-id="b358d-130">Memory</span></span>          | <span data-ttu-id="b358d-131">Открывает выполняющуюся в памяти базу данных.</span><span class="sxs-lookup"><span data-stu-id="b358d-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="b358d-132">Кэш</span><span class="sxs-lookup"><span data-stu-id="b358d-132">Cache</span></span>

<span data-ttu-id="b358d-133">Режим кэширования, используемый при подключении.</span><span class="sxs-lookup"><span data-stu-id="b358d-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="b358d-134">Значение</span><span class="sxs-lookup"><span data-stu-id="b358d-134">Value</span></span>   | <span data-ttu-id="b358d-135">Описание</span><span class="sxs-lookup"><span data-stu-id="b358d-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="b358d-136">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b358d-136">Default</span></span> | <span data-ttu-id="b358d-137">Используется стандартный режим базовой библиотеки SQLite.</span><span class="sxs-lookup"><span data-stu-id="b358d-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="b358d-138">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b358d-138">This is the default.</span></span>                   |
| <span data-ttu-id="b358d-139">Private</span><span class="sxs-lookup"><span data-stu-id="b358d-139">Private</span></span> | <span data-ttu-id="b358d-140">Для каждого подключения используется частный кэш.</span><span class="sxs-lookup"><span data-stu-id="b358d-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="b358d-141">Shared</span><span class="sxs-lookup"><span data-stu-id="b358d-141">Shared</span></span>  | <span data-ttu-id="b358d-142">Для подключений используется общий кэш.</span><span class="sxs-lookup"><span data-stu-id="b358d-142">Connections share a cache.</span></span> <span data-ttu-id="b358d-143">Этот режим может изменить поведение блокировки транзакций и таблиц.</span><span class="sxs-lookup"><span data-stu-id="b358d-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="b358d-144">Пароль</span><span class="sxs-lookup"><span data-stu-id="b358d-144">Password</span></span>

<span data-ttu-id="b358d-145">Ключ шифрования.</span><span class="sxs-lookup"><span data-stu-id="b358d-145">The encryption key.</span></span> <span data-ttu-id="b358d-146">Если указать, `PRAGMA key` отправляется сразу после установки подключения.</span><span class="sxs-lookup"><span data-stu-id="b358d-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="b358d-147">Пароль будет бесполезным, если шифрование не поддерживается нативной библиотекой SQLite.</span><span class="sxs-lookup"><span data-stu-id="b358d-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="b358d-148">Внешние ключи</span><span class="sxs-lookup"><span data-stu-id="b358d-148">Foreign Keys</span></span>

<span data-ttu-id="b358d-149">Значение, которое указывает, следует ли включить ограничения внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="b358d-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="b358d-150">Значение</span><span class="sxs-lookup"><span data-stu-id="b358d-150">Value</span></span>   | <span data-ttu-id="b358d-151">Описание</span><span class="sxs-lookup"><span data-stu-id="b358d-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="b358d-152">Да</span><span class="sxs-lookup"><span data-stu-id="b358d-152">True</span></span>    | <span data-ttu-id="b358d-153">Отправляет `PRAGMA foreign_keys = 1` сразу после установки подключения.</span><span class="sxs-lookup"><span data-stu-id="b358d-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="b358d-154">False</span><span class="sxs-lookup"><span data-stu-id="b358d-154">False</span></span>   | <span data-ttu-id="b358d-155">Отправляет `PRAGMA foreign_keys = 0` сразу после установки подключения.</span><span class="sxs-lookup"><span data-stu-id="b358d-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="b358d-156">(пусто)</span><span class="sxs-lookup"><span data-stu-id="b358d-156">(empty)</span></span> | <span data-ttu-id="b358d-157">Не отправляет `PRAGMA foreign_keys`.</span><span class="sxs-lookup"><span data-stu-id="b358d-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="b358d-158">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b358d-158">This is the default.</span></span> |

<span data-ttu-id="b358d-159">Включать внешние ключи не нужно, если (как в e_sqlite3) для компиляции нативной библиотеки SQLite используется SQLITE_DEFAULT_FOREIGN_KEYS.</span><span class="sxs-lookup"><span data-stu-id="b358d-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="b358d-160">Рекурсивные триггеры</span><span class="sxs-lookup"><span data-stu-id="b358d-160">Recursive triggers</span></span>

<span data-ttu-id="b358d-161">Значение, которое указывает, следует ли разрешить рекурсивные триггеры.</span><span class="sxs-lookup"><span data-stu-id="b358d-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="b358d-162">Значение</span><span class="sxs-lookup"><span data-stu-id="b358d-162">Value</span></span> | <span data-ttu-id="b358d-163">Описание</span><span class="sxs-lookup"><span data-stu-id="b358d-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="b358d-164">Да</span><span class="sxs-lookup"><span data-stu-id="b358d-164">True</span></span>  | <span data-ttu-id="b358d-165">Отправляет `PRAGMA recursive_triggers` сразу после установки подключения.</span><span class="sxs-lookup"><span data-stu-id="b358d-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="b358d-166">False</span><span class="sxs-lookup"><span data-stu-id="b358d-166">False</span></span> | <span data-ttu-id="b358d-167">Не отправляет `PRAGMA recursive_triggers`.</span><span class="sxs-lookup"><span data-stu-id="b358d-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="b358d-168">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b358d-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="b358d-169">Построитель строк подключения</span><span class="sxs-lookup"><span data-stu-id="b358d-169">Connection string builder</span></span>

<span data-ttu-id="b358d-170">Конструктор <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> можно использовать как строго типизированный способ создания строк подключения.</span><span class="sxs-lookup"><span data-stu-id="b358d-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="b358d-171">Он также обеспечивает защиту от атак путем внедрения кода в строку подключения.</span><span class="sxs-lookup"><span data-stu-id="b358d-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="b358d-172">Примеры</span><span class="sxs-lookup"><span data-stu-id="b358d-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="b358d-173">Basic</span><span class="sxs-lookup"><span data-stu-id="b358d-173">Basic</span></span>

<span data-ttu-id="b358d-174">Базовая строка подключения с общим кэшем для оптимизации параллелизма.</span><span class="sxs-lookup"><span data-stu-id="b358d-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="b358d-175">зашифрованные;</span><span class="sxs-lookup"><span data-stu-id="b358d-175">Encrypted</span></span>

<span data-ttu-id="b358d-176">Зашифрованная база данных.</span><span class="sxs-lookup"><span data-stu-id="b358d-176">An encrypted database.</span></span>

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="b358d-177">Только чтение</span><span class="sxs-lookup"><span data-stu-id="b358d-177">Read-only</span></span>

<span data-ttu-id="b358d-178">База данных с доступом только на чтение, которую приложение не может изменить.</span><span class="sxs-lookup"><span data-stu-id="b358d-178">A read-only database that cannot be modified by the app.</span></span>

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="b358d-179">In-memory</span><span class="sxs-lookup"><span data-stu-id="b358d-179">In-memory</span></span>

<span data-ttu-id="b358d-180">Частная выполняющаяся в памяти база данных.</span><span class="sxs-lookup"><span data-stu-id="b358d-180">A private, in-memory database.</span></span>

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="b358d-181">Общая выполняющаяся в памяти база данных</span><span class="sxs-lookup"><span data-stu-id="b358d-181">Sharable in-memory</span></span>

<span data-ttu-id="b358d-182">Общая выполняющаяся в памяти база данных, определяемая по имени *Sharable*.</span><span class="sxs-lookup"><span data-stu-id="b358d-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="b358d-183">См. также</span><span class="sxs-lookup"><span data-stu-id="b358d-183">See also</span></span>

* [<span data-ttu-id="b358d-184">Строки подключения в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b358d-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="b358d-185">Выполняющиеся в памяти базы данных</span><span class="sxs-lookup"><span data-stu-id="b358d-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="b358d-186">Транзакции</span><span class="sxs-lookup"><span data-stu-id="b358d-186">Transactions</span></span>](transactions.md)
