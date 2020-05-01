---
title: Резервное копирование в сети
ms.date: 12/13/2019
description: Узнайте, как использовать функцию резервного копирования в сети в SQLite.
ms.openlocfilehash: d857dcb69f2b2d10b034a0abf222b30c2e20bb41
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901287"
---
# <a name="online-backup"></a><span data-ttu-id="bd3dc-103">Резервное копирование в сети</span><span class="sxs-lookup"><span data-stu-id="bd3dc-103">Online backup</span></span>

<span data-ttu-id="bd3dc-104">SQLite может создавать резервные копии файлов базы данных во время работы приложения.</span><span class="sxs-lookup"><span data-stu-id="bd3dc-104">SQLite can back up database files while the app is running.</span></span> <span data-ttu-id="bd3dc-105">Эту возможность обеспечивает Microsoft. Data. SQLite путем применения метода <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> к `SqliteConnection`.</span><span class="sxs-lookup"><span data-stu-id="bd3dc-105">This functionality is available in Microsoft.Data.Sqlite as the <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> method on `SqliteConnection`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

<span data-ttu-id="bd3dc-106">Команда `BackupDatabase` позволяет максимально быстро создать резервную копию базы данных, заблокировав запись в базу из других подключений.</span><span class="sxs-lookup"><span data-stu-id="bd3dc-106">Currently, `BackupDatabase` will back up the database as quickly as possible and blocks other connections from writing to the database.</span></span> <span data-ttu-id="bd3dc-107">[Здесь](https://github.com/dotnet/efcore/issues/13834) описан альтернативный API для резервного копирования базы данных в фоновом режиме, который позволяет выполнять запись в базу другим подключениям, прерывая резервное копирование.</span><span class="sxs-lookup"><span data-stu-id="bd3dc-107">Issue [#13834](https://github.com/dotnet/efcore/issues/13834) would provide an alternative API to back up the database in the background and allow other connections to interrupt the backup and write to the database.</span></span> <span data-ttu-id="bd3dc-108">На упомянутой странице вы можете поделиться своим мнением.</span><span class="sxs-lookup"><span data-stu-id="bd3dc-108">If you're interested, provide feedback on the issue.</span></span>
