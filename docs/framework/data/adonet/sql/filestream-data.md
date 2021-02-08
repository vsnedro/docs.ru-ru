---
description: 'Дополнительные сведения: данные FILESTREAM'
title: Данные FILESTREAM
ms.date: 03/30/2017
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
ms.openlocfilehash: 0110be6b867a07ec1cd204e2a3de371367bbfa36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802051"
---
# <a name="filestream-data"></a>Данные FILESTREAM

Для двоичных (BLOB) данных, хранимых в столбце varbinary(max), появился новый атрибут хранилища FILESTREAM. Перед созданием FILESTREAM для хранения двоичных данных требовалась специальная обработка. Неструктурированные данные, такие как текстовые документы, изображения и видео, часто хранятся вне базы данных, что затрудняет управление ими.

> [!NOTE]
> Для работы с данными FILESTREAM через SqlClient необходимо установить .NET Framework 3.5 с пакетом обновления 1 (SP1) или более поздней версии.

При указании для столбца varbinary(max) атрибута FILESTREAM сервер SQL Server сохраняет данные не в файле базы данных, а в файловой системе NTFS на локальном компьютере. Хотя эти данные хранятся отдельно, для работы с ними можно использовать те же инструкции Transact-SQL, что и для данных varbinary(max), хранящихся в базе данных.

## <a name="sqlclient-support-for-filestream"></a>Поддержка атрибута FILESTREAM в SqlClient

Платформа .NET Framework поставщик данных для SQL Server, <xref:System.Data.SqlClient> поддерживает чтение и запись данных FILESTREAM с помощью <xref:System.Data.SqlTypes.SqlFileStream> класса, определенного в <xref:System.Data.SqlTypes> пространстве имен. `SqlFileStream` наследует от класса <xref:System.IO.Stream>, который предоставляет методы для чтения и записи в потоки данных. После считывания из потока данные передаются из потока в структуру данных, например массив байтов. Запись передает данные из структуры данных в поток.

### <a name="creating-the-sql-server-table"></a>Создание таблицы SQL Server

Приведенная ниже инструкция Transact-SQL создает таблицу employees и вставляет в нее строку данных. После включения хранилища FILESTREAM эту таблицу можно использовать вместе с приведенными ниже примерами кода. Ссылки на ресурсы электронной документации на SQL Server приведены в конце данного раздела.

```sql
CREATE TABLE employees
(
  EmployeeId INT  NOT NULL  PRIMARY KEY,
  Photo VARBINARY(MAX) FILESTREAM  NULL,
  RowGuid UNIQUEIDENTIFIER  NOT NULL  ROWGUIDCOL
  UNIQUE DEFAULT NEWID()
)
GO
Insert into employees
Values(1, 0x00, default)
GO
```

### <a name="example-reading-overwriting-and-inserting-filestream-data"></a>Пример. Чтение, перезапись и вставка данных FILESTREAM

В приведенном ниже примере демонстрируется чтение данных из потока FILESTREAM. Код получает логический путь к файлу, устанавливая для `FileAccess` значение `Read` и для `FileOptions` — `SequentialScan`. Затем код считывает байты из SqlFileStream и передает их в буфер. Затем байты записываются в окно консоли.

В примере также демонстрируется запись данных в поток FILESTREAM с перезаписью всех существующих данных. Код получает логический путь к файлу и создает `SqlFileStream` устанавливая для `FileAccess` значение `Write` и для `FileOptions` — `SequentialScan`. Один байт записывается в `SqlFileStream`, заменяя все данные в файле.

В приведенном примере также демонстрируется запись данных в поток FILESTREAM с использованием метода Seek для добавления данных в конец файла. Код получает логический путь к файлу и создает `SqlFileStream` устанавливая для `FileAccess` значение `ReadWrite` и для `FileOptions` — `SequentialScan`. Код использует метод Seek для поиска конца файла, добавляя один байт к существующему файлу.

```csharp
using System;
using System.Data.SqlClient;
using System.Data.SqlTypes;
using System.Data;
using System.IO;

namespace FileStreamTest
{
    class Program
    {
        static void Main(string[] args)
        {
            SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder("server=(local);integrated security=true;database=myDB");
            ReadFileStream(builder);
            OverwriteFileStream(builder);
            InsertFileStream(builder);

            Console.WriteLine("Done");
        }

        private static void ReadFileStream(SqlConnectionStringBuilder connStringBuilder)
        {
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))
            {
                connection.Open();
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);

                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);
                command.Transaction = tran;

                using (SqlDataReader reader = command.ExecuteReader())
                {
                    while (reader.Read())
                    {
                        // Get the pointer for the file
                        string path = reader.GetString(0);
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;

                        // Create the SqlFileStream
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Read, FileOptions.SequentialScan, allocationSize: 0))
                        {
                            // Read the contents as bytes and write them to the console
                            for (long index = 0; index < fileStream.Length; index++)
                            {
                                Console.WriteLine(fileStream.ReadByte());
                            }
                        }
                    }
                }
                tran.Commit();
            }
        }

        private static void OverwriteFileStream(SqlConnectionStringBuilder connStringBuilder)
        {
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))
            {
                connection.Open();

                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);

                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);
                command.Transaction = tran;

                using (SqlDataReader reader = command.ExecuteReader())
                {
                    while (reader.Read())
                    {
                        // Get the pointer for file
                        string path = reader.GetString(0);
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;

                        // Create the SqlFileStream
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Write, FileOptions.SequentialScan, allocationSize: 0))
                        {
                            // Write a single byte to the file. This will
                            // replace any data in the file.
                            fileStream.WriteByte(0x01);
                        }
                    }
                }
                tran.Commit();
            }
        }

        private static void InsertFileStream(SqlConnectionStringBuilder connStringBuilder)
        {
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))
            {
                connection.Open();

                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);

                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);
                command.Transaction = tran;

                using (SqlDataReader reader = command.ExecuteReader())
                {
                    while (reader.Read())
                    {
                        // Get the pointer for file
                        string path = reader.GetString(0);
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;

                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.ReadWrite, FileOptions.SequentialScan, allocationSize: 0))
                        {
                            // Seek to the end of the file
                            fileStream.Seek(0, SeekOrigin.End);

                            // Append a single byte
                            fileStream.WriteByte(0x01);
                        }
                    }
                }
                tran.Commit();
            }

        }
    }
}
```

Другой пример см. в разделе [Как сохранять и извлекать двоичные данные в столбце файлового потока](https://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).

## <a name="resources-in-sql-server-books-online"></a>Ресурсы в электронной документации по SQL Server

Полная документация по FILESTREAM содержится в указанных ниже разделах электронной документации на SQL Server.

|Раздел|Описание|
|-----------|-----------------|
|[FILESTREAM (SQL Server)](/sql/relational-databases/blob/filestream-sql-server)|Описывает, когда следует использовать хранилище FILESTREAM, и как оно интегрирует ядро СУБД Microsoft SQL Server с файловой системой NTFS.|
|[Создание клиентских приложений для данных FILESTREAM](/sql/relational-databases/blob/create-client-applications-for-filestream-data)|Описывает функции API Windows для работы с данными FILESTREAM.|
|[FILESTREAM и другие возможности SQL Server](/sql/relational-databases/blob/filestream-compatibility-with-other-sql-server-features)|Содержит рекомендации, направляющие и ограничения для использования данных FILESTREAM с другими функциями SQL Server.|

## <a name="see-also"></a>См. также

- [Типы данных SQL Server и ADO.NET](sql-server-data-types.md)
- [Извлечение и изменение данных в ADO.NET](../retrieving-and-modifying-data.md)
- [Управление доступом для кода и ADO.NET](../code-access-security.md)
- [Двоичные данные и данные больших значений SQL Server](sql-server-binary-and-large-value-data.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
