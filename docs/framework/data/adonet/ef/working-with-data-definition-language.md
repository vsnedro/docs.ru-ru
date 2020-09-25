---
title: Работа с языком описания данных DDL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
ms.openlocfilehash: c30cbbc1eae6d4cbcadb9bfe8d267fb428764971
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200892"
---
# <a name="working-with-data-definition-language"></a>Работа с языком описания данных DDL

Начиная с .NET Framework версии 4 Entity Framework поддерживает язык описания данных (DDL). Это позволяет создавать и удалять экземпляры базы данных с использованием строки подключения и метаданных модели хранения (SSDL).  
  
 В следующих методах в <xref:System.Data.Objects.ObjectContext> с помощью строки соединения и содержимого SSDL выполняются следующие задачи: создание базы данных, удаление базы данных, проверка наличия базы данных и просмотр сформированного скрипта DDL.  
  
- <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
- <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
- <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
- <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
> Предполагается наличие достаточных разрешений для выполнения команд DDL.  
  
 Ранее указанные методы делегируют большую часть работы базовому поставщику данных ADO.NET. Поставщик отвечает за соблюдение соглашения об именах, применяемых при создании объектов базы данных, в соответствии с правилами, используемыми для запросов и обновлений.  
  
 В следующем примере показано, как создать базу данных по существующей модели. Кроме того, новый объект сущности добавляется в контекст объекта, а затем сохраняется в базе данных.  
  
## <a name="procedures"></a>Процедуры  
  
### <a name="to-define-a-database-based-on-the-existing-model"></a>Определение базы данных по существующей модели  
  
1. Создайте консольное приложение.  
  
2. Добавьте существующую модель в приложение.  
  
    1. Добавьте пустую модель с именем `SchoolModel` . Чтобы создать пустую модель, см. раздел [как создать файл EDMX](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100)) .  
  
     В проект будет добавлен файл SchoolModel.edmx.  
  
    1. Скопируйте концептуальное, хранилище и сопоставленное содержимое для модели School из статьи [School Model (учебная модель](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) ).  
  
    2. Откройте файл SchoolModel.edmx и вставьте нужное содержимое в тегах `edmx:Runtime`.  
  
3. Добавьте следующий код в функцию main. Этот код инициализирует строку подключения с сервером базы данных, просматривает скрипт DDL, создает базу данных, добавляет новую сущность в контекст и сохраняет изменения в базе данных.  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]
