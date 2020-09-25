---
title: Владение и отделение пользователей от схем в SQL Server
description: Узнайте, как разделение пользовательских схем обеспечивает гибкость при управлении SQL Server разрешений на объекты базы данных. Схемы группируют объекты в отдельные пространства имен.
ms.date: 03/30/2017
ms.assetid: 242830c1-31b5-4427-828c-cc22ff339f30
ms.openlocfilehash: e92799237a90c502aa4000d8d4027df522aa0d87
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183147"
---
# <a name="ownership-and-user-schema-separation-in-sql-server"></a><span data-ttu-id="e3ef2-104">Владение и отделение пользователей от схем в SQL Server</span><span class="sxs-lookup"><span data-stu-id="e3ef2-104">Ownership and User-Schema Separation in SQL Server</span></span>

<span data-ttu-id="e3ef2-105">Основным принципом безопасности SQL Server является то, что владельцы объектов имеют неотзываемые разрешения на их администрирование.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-105">A core concept of SQL Server security is that owners of objects have irrevocable permissions to administer them.</span></span> <span data-ttu-id="e3ef2-106">Нельзя удалять права доступа у владельцев объектов. Также нельзя удалять пользователей из базы данных, если они владеют в ней объектами.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-106">You cannot remove privileges from an object owner, and you cannot drop users from a database if they own objects in it.</span></span>  
  
## <a name="user-schema-separation"></a><span data-ttu-id="e3ef2-107">Отделение пользователей от схем</span><span class="sxs-lookup"><span data-stu-id="e3ef2-107">User-Schema Separation</span></span>  

 <span data-ttu-id="e3ef2-108">Отделение пользователей от схем обеспечивает дополнительную гибкость в управлении разрешениями объектов базы данных.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-108">User-schema separation allows for more flexibility in managing database object permissions.</span></span> <span data-ttu-id="e3ef2-109">*Схема* — это именованный контейнер для объектов базы данных, который позволяет группировать объекты в отдельные пространства имен.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-109">A *schema* is a named container for database objects, which allows you to group objects into separate namespaces.</span></span> <span data-ttu-id="e3ef2-110">Например, образец базы данных AdventureWorks содержит схемы для Production, Sales и HumanResources.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-110">For example, the AdventureWorks sample database contains schemas for Production, Sales, and HumanResources.</span></span>  
  
 <span data-ttu-id="e3ef2-111">Четырехкомпонентный синтаксис ссылок на объекты указывает имя схемы.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-111">The four-part naming syntax for referring to objects specifies the schema name.</span></span>  
  
```text
Server.Database.DatabaseSchema.DatabaseObject  
```  
  
### <a name="schema-owners-and-permissions"></a><span data-ttu-id="e3ef2-112">Владельцы схемы и разрешения</span><span class="sxs-lookup"><span data-stu-id="e3ef2-112">Schema Owners and Permissions</span></span>  

 <span data-ttu-id="e3ef2-113">Владельцем схемы может быть любой участник базы данных, при этом одному участнику может принадлежать несколько схем.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-113">Schemas can be owned by any database principal, and a single principal can own multiple schemas.</span></span> <span data-ttu-id="e3ef2-114">К схеме можно применить правила безопасности, которые наследуются всеми объектами схемы.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-114">You can apply security rules to a schema, which are inherited by all objects in the schema.</span></span> <span data-ttu-id="e3ef2-115">После установки разрешений доступа для схемы они автоматически применяются по мере добавления к схеме новых объектов.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-115">Once you set up access permissions for a schema, those permissions are automatically applied as new objects are added to the schema.</span></span> <span data-ttu-id="e3ef2-116">Пользователь может назначить новую схему, а несколько пользователей базы данных могут совместно использовать одну одну схему.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-116">Users can be assigned a default schema, and multiple database users can share the same schema.</span></span>  
  
 <span data-ttu-id="e3ef2-117">По умолчанию, если разработчик создает объект в схеме, он принадлежит участнику безопасности, являющемуся владельцем схемы, а не разработчику.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-117">By default, when developers create objects in a schema, the objects are owned by the security principal that owns the schema, not the developer.</span></span> <span data-ttu-id="e3ef2-118">Владение объектом можно передать с помощью инструкции Transact-SQL ALTER AUTHORIZATION.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-118">Object ownership can be transferred with ALTER AUTHORIZATION Transact-SQL statement.</span></span> <span data-ttu-id="e3ef2-119">Схема может также содержать объекты, принадлежащие другим пользователям и иметь более детализированные разрешения, чем назначенные схеме, хотя это не рекомендуется из-за увеличения сложности управления разрешениями.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-119">A schema can also contain objects that are owned by different users and have more granular permissions than those assigned to the schema, although this is not recommended because it adds complexity to managing permissions.</span></span> <span data-ttu-id="e3ef2-120">Объекты можно перемещать из одной схемы в другую, а принадлежность схемы передавать от одного участника другому.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-120">Objects can be moved between schemas, and schema ownership can be transferred between principals.</span></span> <span data-ttu-id="e3ef2-121">Пользователей базы данных можно удалять, не влияя этим на схемы.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-121">Database users can be dropped without affecting schemas.</span></span>  
  
### <a name="built-in-schemas"></a><span data-ttu-id="e3ef2-122">Встроенные схемы</span><span class="sxs-lookup"><span data-stu-id="e3ef2-122">Built-In Schemas</span></span>  

 <span data-ttu-id="e3ef2-123">SQL Server поставляется с десятью предварительно определенными схемами, имеющими одинаковое имя со встроенными пользователями и ролями базы данных.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-123">SQL Server ships with ten pre-defined schemas that have the same names as the built-in database users and roles.</span></span> <span data-ttu-id="e3ef2-124">Они существуют главным образом ради обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-124">These exist mainly for backward compatibility.</span></span> <span data-ttu-id="e3ef2-125">Схемы, имеющие одинаковые имена с предопределенными ролями базы данных, можно удалить, если они не нужны.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-125">You can drop the schemas that have the same names as the fixed database roles if you do not need them.</span></span> <span data-ttu-id="e3ef2-126">Нельзя удалить следующие схемы.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-126">You cannot drop the following schemas:</span></span>  
  
- `dbo`  
  
- `guest`  
  
- `sys`  
  
- `INFORMATION_SCHEMA`  
  
 <span data-ttu-id="e3ef2-127">Если их удалить из шаблона базы данных, эти схемы не появятся в новых базах данных.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-127">If you drop them from the model database, they will not appear in new databases.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e3ef2-128">Схемы `sys` и `INFORMATION_SCHEMA` зарезервированы для системных объектов.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-128">The `sys` and `INFORMATION_SCHEMA` schemas are reserved for system objects.</span></span> <span data-ttu-id="e3ef2-129">В этих схемах нельзя создавать и удалять объекты.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-129">You cannot create objects in these schemas and you cannot drop them.</span></span>  
  
#### <a name="the-dbo-schema"></a><span data-ttu-id="e3ef2-130">Схема dbo</span><span class="sxs-lookup"><span data-stu-id="e3ef2-130">The dbo Schema</span></span>  

 <span data-ttu-id="e3ef2-131">Схема `dbo` представляет собой схему по умолчанию для вновь созданной базы данных.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-131">The `dbo` schema is the default schema for a newly created database.</span></span> <span data-ttu-id="e3ef2-132">Владельцем схемы `dbo` является учетная запись пользователя `dbo`.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-132">The `dbo` schema is owned by the `dbo` user account.</span></span> <span data-ttu-id="e3ef2-133">Схемой по умолчанию для пользователей, созданных с помощью команды Transact-SQL CREATE USER, является `dbo`.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-133">By default, users created with the CREATE USER Transact-SQL command have `dbo` as their default schema.</span></span>  
  
 <span data-ttu-id="e3ef2-134">Пользователи, которым назначена схема `dbo`, не наследуют разрешения пользовательской учетной записи `dbo`.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-134">Users who are assigned the `dbo` schema do not inherit the permissions of the `dbo` user account.</span></span> <span data-ttu-id="e3ef2-135">Пользователи не наследуют разрешения схемы, их наследуют объекты базы данных, содержащиеся в схеме.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-135">No permissions are inherited from a schema by users; schema permissions are inherited by the database objects contained in the schema.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e3ef2-136">Если на объект базы данных ссылаются с помощью однокомпонентного имени, SQL Server вначале ищет этот объект в схеме пользователя по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-136">When database objects are referenced by using a one-part name, SQL Server first looks in the user's default schema.</span></span> <span data-ttu-id="e3ef2-137">Если объект не найден, SQL Server ищет его в схеме `dbo`.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-137">If the object is not found there, SQL Server looks next in the `dbo` schema.</span></span> <span data-ttu-id="e3ef2-138">Если этот объект не найден в схеме `dbo`, возвращается ошибка.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-138">If the object is not in the `dbo` schema, an error is returned.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="e3ef2-139">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="e3ef2-139">External Resources</span></span>  

 <span data-ttu-id="e3ef2-140">Дополнительные сведения о принадлежности объектов и схемах см. в следующих документах.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-140">For more information on object ownership and schemas, see the following resources.</span></span>  
  
|<span data-ttu-id="e3ef2-141">Ресурс</span><span class="sxs-lookup"><span data-stu-id="e3ef2-141">Resource</span></span>|<span data-ttu-id="e3ef2-142">Описание</span><span class="sxs-lookup"><span data-stu-id="e3ef2-142">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="e3ef2-143">[Отделение пользователей от схем](/previous-versions/sql/sql-server-2008-r2/ms190387(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="e3ef2-143">[User-Schema Separation](/previous-versions/sql/sql-server-2008-r2/ms190387(v=sql.105))</span></span>|<span data-ttu-id="e3ef2-144">Описывает изменения, возникшие из-за отделения пользователей от схем.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-144">Describes the changes introduced by user-schema separation.</span></span> <span data-ttu-id="e3ef2-145">Сюда входит новое поведение, его влияние на владение, представления каталогов и разрешения.</span><span class="sxs-lookup"><span data-stu-id="e3ef2-145">Includes new behavior, its impact on ownership, catalog views, and permissions.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3ef2-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e3ef2-146">See also</span></span>

- [<span data-ttu-id="e3ef2-147">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e3ef2-147">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="e3ef2-148">Сценарии безопасности приложений в SQL Server</span><span class="sxs-lookup"><span data-stu-id="e3ef2-148">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="e3ef2-149">Аутентификация в SQL Server</span><span class="sxs-lookup"><span data-stu-id="e3ef2-149">Authentication in SQL Server</span></span>](authentication-in-sql-server.md)
- [<span data-ttu-id="e3ef2-150">Роли сервера и базы данных в SQL Server</span><span class="sxs-lookup"><span data-stu-id="e3ef2-150">Server and Database Roles in SQL Server</span></span>](server-and-database-roles-in-sql-server.md)
- [<span data-ttu-id="e3ef2-151">Авторизация и разрешения в SQL Server</span><span class="sxs-lookup"><span data-stu-id="e3ef2-151">Authorization and Permissions in SQL Server</span></span>](authorization-and-permissions-in-sql-server.md)
- [<span data-ttu-id="e3ef2-152">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e3ef2-152">ADO.NET Overview</span></span>](../ado-net-overview.md)
