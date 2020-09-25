---
title: Поддержка SqlClient LocalDB
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 841c455605b0b32668d26cab16a6207dc1c0f716
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203427"
---
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="3cb16-102">Поддержка SqlClient LocalDB</span><span class="sxs-lookup"><span data-stu-id="3cb16-102">SqlClient Support for LocalDB</span></span>

<span data-ttu-id="3cb16-103">Начиная с названия кода Denali в SQL Server, будет доступна облегченная версия SQL Server, называемая LocalDB.</span><span class="sxs-lookup"><span data-stu-id="3cb16-103">Beginning in SQL Server code name Denali, a lightweight version of SQL Server, called LocalDB, will be available.</span></span> <span data-ttu-id="3cb16-104">В этом разделе обсуждаются способы подключения к базе данных в LocalDB.</span><span class="sxs-lookup"><span data-stu-id="3cb16-104">This topic discusses how to connect to a LocalDB database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cb16-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="3cb16-105">Remarks</span></span>  

 <span data-ttu-id="3cb16-106">Дополнительные сведения о LocalDB, включая способы его установки и настройки, см. в электронной документации на SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3cb16-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="3cb16-107">Чтобы получить сводные сведения о возможностях работы с LocalDB, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="3cb16-107">To summarize what you can do with LocalDB:</span></span>  
  
- <span data-ttu-id="3cb16-108">Создайте и запустите экземпляры LocalDB с помощью sqllocaldb.exe или файла app.config.</span><span class="sxs-lookup"><span data-stu-id="3cb16-108">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
- <span data-ttu-id="3cb16-109">Для добавления и изменения баз данных в локальном экземпляре LocalDB можно воспользоваться программой sqlcmd.exe.</span><span class="sxs-lookup"><span data-stu-id="3cb16-109">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="3cb16-110">Например, `sqlcmd -S (localdb)\myinst`.</span><span class="sxs-lookup"><span data-stu-id="3cb16-110">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
- <span data-ttu-id="3cb16-111">Используйте ключевое слово строки подключения `AttachDBFilename`, чтобы добавить базу данных в экземпляр LocalDB.</span><span class="sxs-lookup"><span data-stu-id="3cb16-111">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="3cb16-112">Если при использовании `AttachDBFilename` не указано имя базы данных в ключевом слове строки подключения `Database`, то база данных будет удалена из экземпляра LocalDB при закрытии приложения.</span><span class="sxs-lookup"><span data-stu-id="3cb16-112">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
- <span data-ttu-id="3cb16-113">Чтобы указать экземпляр LocalDB в строке подключения, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3cb16-113">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="3cb16-114">Например, у вас есть экземпляр с именем `myInstance`, строка подключения будет включать:</span><span class="sxs-lookup"><span data-stu-id="3cb16-114">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    `server=(localdb)\\myInstance`  
  
 <span data-ttu-id="3cb16-115">`User Instance=True` не допускается при подключении к базе данных LocalDB.</span><span class="sxs-lookup"><span data-stu-id="3cb16-115">`User Instance=True` is not allowed when connecting to a LocalDB database.</span></span>  
  
 <span data-ttu-id="3cb16-116">Базу данных LocalDB можно скачать из [пакета дополнительных компонентов Microsoft SQL Server 2012](https://www.microsoft.com/download/en/details.aspx?id=29065).</span><span class="sxs-lookup"><span data-stu-id="3cb16-116">You can download LocalDB from [Microsoft SQL Server 2012 Feature Pack](https://www.microsoft.com/download/en/details.aspx?id=29065).</span></span> <span data-ttu-id="3cb16-117">Если необходимо изменение данных в экземпляре LocalDB с помощью программы sqlcmd.exe, то необходимо пользоваться версией sqlcmd из SQL Server 2012. Эту программу можно также получить из пакета дополнительных компонентов SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="3cb16-117">If you will use sqlcmd.exe to modify data in your LocalDB instance, you will need sqlcmd from SQL Server 2012, which you can also get from the SQL Server 2012 Feature Pack.</span></span>  
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="3cb16-118">Создание именованного экземпляра программным путем</span><span class="sxs-lookup"><span data-stu-id="3cb16-118">Programmatically Create a Named Instance</span></span>  

 <span data-ttu-id="3cb16-119">Приложение может создать именованный экземпляр и указать базу данных, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="3cb16-119">An application can create a named instance and specify a database as follows:</span></span>  
  
- <span data-ttu-id="3cb16-120">Укажите экземпляры LocalDB, чтобы добавить в файл app.config сведения, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="3cb16-120">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="3cb16-121">Номер версии экземпляра должен совпадать с номером версии установки LocalDB.</span><span class="sxs-lookup"><span data-stu-id="3cb16-121">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
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
  
- <span data-ttu-id="3cb16-122">Укажите имя экземпляра с помощью ключевого слова строки подключения `server`.</span><span class="sxs-lookup"><span data-stu-id="3cb16-122">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="3cb16-123">Имя экземпляра, указанное в ключевом слове строки подключения `server`, должно соответствовать имени, указанному в файле app.config.</span><span class="sxs-lookup"><span data-stu-id="3cb16-123">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
- <span data-ttu-id="3cb16-124">Используйте ключевое слово строки подключения `AttachDBFilename`, чтобы указать MDF-файл.</span><span class="sxs-lookup"><span data-stu-id="3cb16-124">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cb16-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3cb16-125">See also</span></span>

- [<span data-ttu-id="3cb16-126">SQL Server функций и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3cb16-126">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)
- [<span data-ttu-id="3cb16-127">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3cb16-127">ADO.NET Overview</span></span>](../ado-net-overview.md)
