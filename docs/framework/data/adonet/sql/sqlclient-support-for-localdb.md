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
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="3ae70-102">Поддержка SqlClient LocalDB</span><span class="sxs-lookup"><span data-stu-id="3ae70-102">SqlClient Support for LocalDB</span></span>

<span data-ttu-id="3ae70-103">В этой статье описывается, как подключиться к базе данных LocalDB.</span><span class="sxs-lookup"><span data-stu-id="3ae70-103">This article discusses how to connect to a LocalDB database.</span></span> <span data-ttu-id="3ae70-104">LocalDB — это упрощенная версия SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3ae70-104">LocalDB is a lightweight version of SQL Server.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="3ae70-105">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3ae70-105">Remarks</span></span>
  
 <span data-ttu-id="3ae70-106">Чтобы получить сводные сведения о возможностях работы с LocalDB, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="3ae70-106">To summarize what you can do with LocalDB:</span></span>  
  
- <span data-ttu-id="3ae70-107">Создайте и запустите экземпляры LocalDB с помощью sqllocaldb.exe или файла app.config.</span><span class="sxs-lookup"><span data-stu-id="3ae70-107">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
- <span data-ttu-id="3ae70-108">Для добавления и изменения баз данных в локальном экземпляре LocalDB можно воспользоваться программой sqlcmd.exe.</span><span class="sxs-lookup"><span data-stu-id="3ae70-108">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="3ae70-109">Например, `sqlcmd -S (localdb)\myinst`.</span><span class="sxs-lookup"><span data-stu-id="3ae70-109">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
- <span data-ttu-id="3ae70-110">Используйте ключевое слово строки подключения `AttachDBFilename`, чтобы добавить базу данных в экземпляр LocalDB.</span><span class="sxs-lookup"><span data-stu-id="3ae70-110">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="3ae70-111">Если при использовании `AttachDBFilename` не указано имя базы данных в ключевом слове строки подключения `Database`, то база данных будет удалена из экземпляра LocalDB при закрытии приложения.</span><span class="sxs-lookup"><span data-stu-id="3ae70-111">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
- <span data-ttu-id="3ae70-112">Чтобы указать экземпляр LocalDB в строке подключения, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3ae70-112">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="3ae70-113">Например, у вас есть экземпляр с именем `myInstance`, строка подключения будет включать:</span><span class="sxs-lookup"><span data-stu-id="3ae70-113">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    `server=(localdb)\\myInstance`  
  
 <span data-ttu-id="3ae70-114">`User Instance=True` не допускается при подключении к базе данных LocalDB.</span><span class="sxs-lookup"><span data-stu-id="3ae70-114">`User Instance=True` is not allowed when connecting to a LocalDB database.</span></span>  
  
<span data-ttu-id="3ae70-115">Сведения об установке LocalDB см. в разделе [SQL Server Express LocalDB](/sql/database-engine/configure-windows/sql-server-express-localdb).</span><span class="sxs-lookup"><span data-stu-id="3ae70-115">For information about installing LocalDB, see [SQL Server Express LocalDB](/sql/database-engine/configure-windows/sql-server-express-localdb).</span></span>
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="3ae70-116">Создание именованного экземпляра программным путем</span><span class="sxs-lookup"><span data-stu-id="3ae70-116">Programmatically Create a Named Instance</span></span>  

 <span data-ttu-id="3ae70-117">Приложение может создать именованный экземпляр и указать базу данных, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="3ae70-117">An application can create a named instance and specify a database as follows:</span></span>  
  
- <span data-ttu-id="3ae70-118">Укажите экземпляры LocalDB, чтобы добавить в файл app.config сведения, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="3ae70-118">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="3ae70-119">Номер версии экземпляра должен совпадать с номером версии установки LocalDB.</span><span class="sxs-lookup"><span data-stu-id="3ae70-119">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
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
  
- <span data-ttu-id="3ae70-120">Укажите имя экземпляра с помощью ключевого слова строки подключения `server`.</span><span class="sxs-lookup"><span data-stu-id="3ae70-120">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="3ae70-121">Имя экземпляра, указанное в ключевом слове строки подключения `server`, должно соответствовать имени, указанному в файле app.config.</span><span class="sxs-lookup"><span data-stu-id="3ae70-121">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
- <span data-ttu-id="3ae70-122">Используйте ключевое слово строки подключения `AttachDBFilename`, чтобы указать MDF-файл.</span><span class="sxs-lookup"><span data-stu-id="3ae70-122">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ae70-123">См. также статью</span><span class="sxs-lookup"><span data-stu-id="3ae70-123">See also</span></span>

- [<span data-ttu-id="3ae70-124">Возможности SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3ae70-124">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)
- [<span data-ttu-id="3ae70-125">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3ae70-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
