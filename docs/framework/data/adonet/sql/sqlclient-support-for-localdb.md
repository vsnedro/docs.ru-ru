---
title: Поддержка SqlClient LocalDB
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 55ab1346de6f5c14f15d01344a984c18edf30e02
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824484"
---
# <a name="sqlclient-support-for-localdb"></a>Поддержка SqlClient LocalDB

В этой статье описывается, как подключиться к базе данных LocalDB. LocalDB — это упрощенная версия SQL Server.
  
## <a name="remarks"></a>Комментарии
  
 Чтобы получить сводные сведения о возможностях работы с LocalDB, выполните следующие действия.  
  
- Создайте и запустите экземпляры LocalDB с помощью sqllocaldb.exe или файла app.config.  
  
- Для добавления и изменения баз данных в локальном экземпляре LocalDB можно воспользоваться программой sqlcmd.exe. Например, `sqlcmd -S (localdb)\myinst`.  
  
- Используйте ключевое слово строки подключения `AttachDBFilename`, чтобы добавить базу данных в экземпляр LocalDB. Если при использовании `AttachDBFilename` не указано имя базы данных в ключевом слове строки подключения `Database`, то база данных будет удалена из экземпляра LocalDB при закрытии приложения.  
  
- Чтобы указать экземпляр LocalDB в строке подключения, выполните указанные ниже действия. Например, у вас есть экземпляр с именем `myInstance`, строка подключения будет включать:  
  
    `server=(localdb)\\myInstance`  
  
 `User Instance=True` не допускается при подключении к базе данных LocalDB.  
  
Сведения об установке LocalDB см. в разделе [SQL Server Express LocalDB](/sql/database-engine/configure-windows/sql-server-express-localdb).
  
## <a name="programmatically-create-a-named-instance"></a>Создание именованного экземпляра программным путем  

 Приложение может создать именованный экземпляр и указать базу данных, как показано ниже.  
  
- Укажите экземпляры LocalDB, чтобы добавить в файл app.config сведения, как показано ниже.  Номер версии экземпляра должен совпадать с номером версии установки LocalDB.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <configSections>  
        <section  
        name="system.data.localdb"  
        type="System.Data.LocalDBConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/>  
      </configSections>  
      <system.data.localdb>  
        <localdbinstances>  
          <add name="myInstance" version="11.0" />  
        </localdbinstances>  
      </system.data.localdb>  
    </configuration>  
    ```  
  
- Укажите имя экземпляра с помощью ключевого слова строки подключения `server`.  Имя экземпляра, указанное в ключевом слове строки подключения `server`, должно соответствовать имени, указанному в файле app.config.  
  
- Используйте ключевое слово строки подключения `AttachDBFilename`, чтобы указать MDF-файл.  
  
## <a name="see-also"></a>См. также статью

- [Возможности SQL Server и ADO.NET](sql-server-features-and-adonet.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
