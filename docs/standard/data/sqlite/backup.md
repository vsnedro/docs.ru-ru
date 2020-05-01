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
# <a name="online-backup"></a>Резервное копирование в сети

SQLite может создавать резервные копии файлов базы данных во время работы приложения. Эту возможность обеспечивает Microsoft. Data. SQLite путем применения метода <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> к `SqliteConnection`.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

Команда `BackupDatabase` позволяет максимально быстро создать резервную копию базы данных, заблокировав запись в базу из других подключений. [Здесь](https://github.com/dotnet/efcore/issues/13834) описан альтернативный API для резервного копирования базы данных в фоновом режиме, который позволяет выполнять запись в базу другим подключениям, прерывая резервное копирование. На упомянутой странице вы можете поделиться своим мнением.
