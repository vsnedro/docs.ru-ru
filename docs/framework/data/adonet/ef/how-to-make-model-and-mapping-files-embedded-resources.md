---
title: Практическое руководство. Создание встроенных ресурсов файлов модели и сопоставления
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: aaab2ccc96497cb718b868f7ac63995ad4ba35c8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546683"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="748dd-102">Практическое руководство. Создание встроенных ресурсов файлов модели и сопоставления</span><span class="sxs-lookup"><span data-stu-id="748dd-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="748dd-103">Entity Framework позволяет развертывать файлы модели и сопоставления как внедренные ресурсы приложения.</span><span class="sxs-lookup"><span data-stu-id="748dd-103">The Entity Framework enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="748dd-104">Сборка с внедренными файлами моделей и сопоставления должна быть загружена в том же домене приложения, что и соединение сущности.</span><span class="sxs-lookup"><span data-stu-id="748dd-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="748dd-105">Дополнительные сведения см. в статье [Connection Strings](connection-strings.md) (Строки подключения).</span><span class="sxs-lookup"><span data-stu-id="748dd-105">For more information, see [Connection Strings](connection-strings.md).</span></span> <span data-ttu-id="748dd-106">По умолчанию средства EDM внедряют файлы модели и сопоставления.</span><span class="sxs-lookup"><span data-stu-id="748dd-106">By default, the Entity Data Model tools embed the model and mapping files.</span></span> <span data-ttu-id="748dd-107">При определении файлов модели и сопоставления вручную используйте эту процедуру, чтобы убедиться, что файлы развертываются как внедренные ресурсы вместе с приложением Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="748dd-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an Entity Framework application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="748dd-108">Чтобы обеспечить поддержку внедренных ресурсов, необходимо повторить эту процедуру после каждого изменения файлов модели и сопоставления.</span><span class="sxs-lookup"><span data-stu-id="748dd-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="748dd-109">Внедрение файлов модели и сопоставления</span><span class="sxs-lookup"><span data-stu-id="748dd-109">To embed model and mapping files</span></span>  
  
1. <span data-ttu-id="748dd-110">В **Обозреватель решений**выберите концептуальный файл (CSDL).</span><span class="sxs-lookup"><span data-stu-id="748dd-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2. <span data-ttu-id="748dd-111">На панели **Свойства** задайте для параметра **действие при сборке** значение **внедренный ресурс**.</span><span class="sxs-lookup"><span data-stu-id="748dd-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3. <span data-ttu-id="748dd-112">Повторите шаги 1 и 2 для файла хранения с расширением SSDL и файла сопоставления с расширением MSL.</span><span class="sxs-lookup"><span data-stu-id="748dd-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4. <span data-ttu-id="748dd-113">В **Обозреватель решений**дважды щелкните файл App.config и измените `Metadata` параметр в `connectionString` атрибуте, используя один из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="748dd-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    - <span data-ttu-id="748dd-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="748dd-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span></span>  
  
    - <span data-ttu-id="748dd-115">`Metadata=` `res://*/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="748dd-115">`Metadata=` `res://*/<resourceName>;`</span></span>  
  
    - `Metadata=res://*;`  
  
     <span data-ttu-id="748dd-116">Дополнительные сведения см. в статье [Connection Strings](connection-strings.md) (Строки подключения).</span><span class="sxs-lookup"><span data-stu-id="748dd-116">For more information, see [Connection Strings](connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="748dd-117">Пример</span><span class="sxs-lookup"><span data-stu-id="748dd-117">Example</span></span>  
 <span data-ttu-id="748dd-118">Следующая строка подключения ссылается на внедренную модель и файлы сопоставления для [модели AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="748dd-118">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="748dd-119">Эта строка соединения хранится в файле App.config проекта.</span><span class="sxs-lookup"><span data-stu-id="748dd-119">This connection string is stored in the project's App.config file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="748dd-120">См. также</span><span class="sxs-lookup"><span data-stu-id="748dd-120">See also</span></span>

- [<span data-ttu-id="748dd-121">Моделирование и сопоставление</span><span class="sxs-lookup"><span data-stu-id="748dd-121">Modeling and Mapping</span></span>](modeling-and-mapping.md)
- [<span data-ttu-id="748dd-122">Практическое руководство. Определение строки соединения</span><span class="sxs-lookup"><span data-stu-id="748dd-122">How to: Define the Connection String</span></span>](how-to-define-the-connection-string.md)
- [<span data-ttu-id="748dd-123">Практическое руководство. Сборка строки соединения EntityConnection</span><span class="sxs-lookup"><span data-stu-id="748dd-123">How to: Build an EntityConnection Connection String</span></span>](how-to-build-an-entityconnection-connection-string.md)
- <span data-ttu-id="748dd-124">[Средства EDM ADO.NET](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="748dd-124">[ADO.NET Entity Data Model Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
