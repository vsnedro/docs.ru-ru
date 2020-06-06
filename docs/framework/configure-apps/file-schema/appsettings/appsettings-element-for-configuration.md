---
title: Элемент <appSettings> для <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: ea341d562f4b163a3a1771da0f20903b7d64bcdf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155535"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="b3161-102">Элемент \<appSettings> для \<configuration></span><span class="sxs-lookup"><span data-stu-id="b3161-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="b3161-103">Содержит пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="b3161-103">Contains custom application settings.</span></span> <span data-ttu-id="b3161-104">Это предварительно определенный раздел конфигурации, предоставляемый .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b3161-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="b3161-105">[**\<configuration>**](../configuration-element.md) &nbsp;&nbsp;**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="b3161-105">[**\<configuration>**](../configuration-element.md) &nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b3161-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3161-106">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="b3161-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b3161-107">Attribute</span></span>

|           | <span data-ttu-id="b3161-108">Описание</span><span class="sxs-lookup"><span data-stu-id="b3161-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="b3161-109">**File**</span><span class="sxs-lookup"><span data-stu-id="b3161-109">**file**</span></span>  | <span data-ttu-id="b3161-110">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b3161-110">Optional attribute.</span></span><br><br><span data-ttu-id="b3161-111">Указывает относительный путь к внешнему файлу, содержащему настраиваемые параметры конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="b3161-111">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="b3161-112">Указанный файл содержит те же параметры, что указаны в **\<add>** **\<remove>** элементах, и, **\<clear>** и использует тот же формат пар "ключ-значение", что и эти элементы.</span><span class="sxs-lookup"><span data-stu-id="b3161-112">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="b3161-113">Путь указан относительно основного файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b3161-113">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="b3161-114">Для Windows Forms приложения это двоичная папка (например, */бин/дебуг*), а не расположение файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="b3161-114">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="b3161-115">Для приложений веб-форм путь определяется относительно корневого каталога приложения, где находится файл *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="b3161-115">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="b3161-116">Среда выполнения игнорирует атрибут, если не удается найти указанный файл.</span><span class="sxs-lookup"><span data-stu-id="b3161-116">The runtime ignores the attribute if the specified file can't be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="b3161-117">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="b3161-117">Parent element</span></span>

|     | <span data-ttu-id="b3161-118">Описание</span><span class="sxs-lookup"><span data-stu-id="b3161-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b3161-119">**\<configuration>** Дерев</span><span class="sxs-lookup"><span data-stu-id="b3161-119">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="b3161-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b3161-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="b3161-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b3161-121">Child elements</span></span>

|     | <span data-ttu-id="b3161-122">Описание</span><span class="sxs-lookup"><span data-stu-id="b3161-122">Description</span></span> |
| --- | ----------- |
| [**\<add>**](add-element-for-appsettings.md) | <span data-ttu-id="b3161-123">Добавляет пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="b3161-123">Adds a custom application setting.</span></span> |
| [**\<clear>**](clear-element-for-appsettings.md) | <span data-ttu-id="b3161-124">Удаляет все ранее определенные параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="b3161-124">Clears all previously defined application settings.</span></span> |
| [**\<remove>**](remove-element-for-appsettings.md) | <span data-ttu-id="b3161-125">Удаляет ранее определенный параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="b3161-125">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b3161-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="b3161-126">Remarks</span></span>

<span data-ttu-id="b3161-127">**\<appSettings>** Элемент хранит сведения о конфигурации пользовательского приложения, такие как строки подключения к базе данных, пути к файлам, URL-адреса XML или другие пользовательские сведения о конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="b3161-127">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="b3161-128">Пары "ключ-значение", указанные в **\<appSettings>** элементе, доступны в коде с помощью <xref:System.Configuration.ConfigurationSettings> класса.</span><span class="sxs-lookup"><span data-stu-id="b3161-128">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="b3161-129">Атрибут **File** можно использовать в **\<appSettings>** элементе файла *Web. config* и в файлах конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="b3161-129">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="b3161-130">Этот атрибут задает файл конфигурации, предоставляющий дополнительные параметры или переопределяющий параметры, указанные в **\<appSettings>** элементе.</span><span class="sxs-lookup"><span data-stu-id="b3161-130">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="b3161-131">Атрибут **File** может использоваться в сценариях разработки группы управления исходным кодом, например, когда пользователь хочет переопределить параметры проекта, указанные в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="b3161-131">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="b3161-132">Файлы конфигурации, заданные атрибутом **File** , должны иметь корневой узел, **\<appSettings>** а не **\<configuration>** .</span><span class="sxs-lookup"><span data-stu-id="b3161-132">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="b3161-133">Пример</span><span class="sxs-lookup"><span data-stu-id="b3161-133">Example</span></span>

<span data-ttu-id="b3161-134">В приведенном ниже примере показан внешний файл параметров приложения (*custom.config*), в котором определен пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="b3161-134">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="b3161-135">В приведенном ниже примере показан файл конфигурации приложения, в котором используется параметр из внешнего файла параметров и задается собственный параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="b3161-135">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="b3161-136">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="b3161-136">Configuration file</span></span>

<span data-ttu-id="b3161-137">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="b3161-137">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3161-138">См. также</span><span class="sxs-lookup"><span data-stu-id="b3161-138">See also</span></span>

- [<span data-ttu-id="b3161-139">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b3161-139">Configuration file schema for the .NET Framework</span></span>](../index.md)
