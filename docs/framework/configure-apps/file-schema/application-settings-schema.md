---
title: Схема настройки приложений
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 90d471888950347c041b4824b659ce33fda512d7
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242833"
---
# <a name="application-settings-schema"></a><span data-ttu-id="de5fc-102">Схема настройки приложений</span><span class="sxs-lookup"><span data-stu-id="de5fc-102">Application Settings schema</span></span>

<span data-ttu-id="de5fc-103">Настройки приложений позволяют приложению Windows Forms или ASP.NET для хранения и извлечения параметров, с тем чтобы с развернуть приложения и пользовательские настройки.</span><span class="sxs-lookup"><span data-stu-id="de5fc-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="de5fc-104">В этом контексте *параметр* представляет собой любую информацию, которая может быть специфична для приложения или специфична для текущего пользователя - от строки подключения базы данных до предпочтительного размера окна по умолчанию пользователя.</span><span class="sxs-lookup"><span data-stu-id="de5fc-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="de5fc-105">По умолчанию настройки приложения в приложении Windows Forms используют <xref:System.Configuration.LocalFileSettingsProvider> класс, который использует систему конфигурации .NET для хранения настроек в файле конфигурации XML.</span><span class="sxs-lookup"><span data-stu-id="de5fc-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="de5fc-106">Для получения дополнительной информации о файлах, используемых настройками приложений, [см.](../../winforms/advanced/application-settings-architecture.md)</span><span class="sxs-lookup"><span data-stu-id="de5fc-106">For more information about the files used by application settings, see [Application Settings Architecture](../../winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="de5fc-107">Настройки приложения определяют следующие элементы как часть используемых файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="de5fc-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="de5fc-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="de5fc-108">Element</span></span>                    | <span data-ttu-id="de5fc-109">Описание</span><span class="sxs-lookup"><span data-stu-id="de5fc-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="de5fc-110">**\<applicationSettings>**</span><span class="sxs-lookup"><span data-stu-id="de5fc-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="de5fc-111">Содержит все \*\* \<настройки>\*\* теги, специфичные для приложения.</span><span class="sxs-lookup"><span data-stu-id="de5fc-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="de5fc-112">**\<userSettings>**</span><span class="sxs-lookup"><span data-stu-id="de5fc-112">**\<userSettings>**</span></span>        | <span data-ttu-id="de5fc-113">Содержит все \*\* \<настройки>\*\* теги, специфичные для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="de5fc-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="de5fc-114">**\<установка>**</span><span class="sxs-lookup"><span data-stu-id="de5fc-114">**\<setting>**</span></span>             | <span data-ttu-id="de5fc-115">Определяет параметр.</span><span class="sxs-lookup"><span data-stu-id="de5fc-115">Defines a setting.</span></span> <span data-ttu-id="de5fc-116">Ребенок либо \*\* \<>приложений, либо\*\* \*\* \<>userSettings. \*\*</span><span class="sxs-lookup"><span data-stu-id="de5fc-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="de5fc-117">**\<значение>**</span><span class="sxs-lookup"><span data-stu-id="de5fc-117">**\<value>**</span></span>               | <span data-ttu-id="de5fc-118">Определяет значение параметра.</span><span class="sxs-lookup"><span data-stu-id="de5fc-118">Defines a setting's value.</span></span> <span data-ttu-id="de5fc-119">Ребенок \*\* \<установки>\*\*.</span><span class="sxs-lookup"><span data-stu-id="de5fc-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="de5fc-120">\<applicationSettings> элемент</span><span class="sxs-lookup"><span data-stu-id="de5fc-120">\<applicationSettings> element</span></span>

<span data-ttu-id="de5fc-121">Этот элемент содержит все \*\* \<настройки>\*\* теги, которые являются специфическими для экземпляра приложения на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="de5fc-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="de5fc-122">Атрибуты не определяются.</span><span class="sxs-lookup"><span data-stu-id="de5fc-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="de5fc-123">\<userSettings> элемент</span><span class="sxs-lookup"><span data-stu-id="de5fc-123">\<userSettings> element</span></span>

<span data-ttu-id="de5fc-124">Этот элемент содержит все \*\* \<настройки>\*\* теги, которые являются специфическими для пользователя, который в настоящее время использует приложение.</span><span class="sxs-lookup"><span data-stu-id="de5fc-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="de5fc-125">Атрибуты не определяются.</span><span class="sxs-lookup"><span data-stu-id="de5fc-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="de5fc-126">\<установка элемента></span><span class="sxs-lookup"><span data-stu-id="de5fc-126">\<setting> element</span></span>

<span data-ttu-id="de5fc-127">Этот элемент определяет настройки.</span><span class="sxs-lookup"><span data-stu-id="de5fc-127">This element defines a setting.</span></span> <span data-ttu-id="de5fc-128">Он имеет следующие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="de5fc-128">It has the following attributes.</span></span>

| <span data-ttu-id="de5fc-129">Атрибут</span><span class="sxs-lookup"><span data-stu-id="de5fc-129">Attribute</span></span>        | <span data-ttu-id="de5fc-130">Описание</span><span class="sxs-lookup"><span data-stu-id="de5fc-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="de5fc-131">**name**</span><span class="sxs-lookup"><span data-stu-id="de5fc-131">**name**</span></span>         | <span data-ttu-id="de5fc-132">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="de5fc-132">Required.</span></span> <span data-ttu-id="de5fc-133">Уникальный идентификатор настройки.</span><span class="sxs-lookup"><span data-stu-id="de5fc-133">The unique ID of the setting.</span></span> <span data-ttu-id="de5fc-134">Настройки, созданные через Visual `ProjectName.Properties.Settings`Studio, сохраняются с именем.</span><span class="sxs-lookup"><span data-stu-id="de5fc-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="de5fc-135">**serializeAs**</span><span class="sxs-lookup"><span data-stu-id="de5fc-135">**serializeAs**</span></span> | <span data-ttu-id="de5fc-136">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="de5fc-136">Required.</span></span> <span data-ttu-id="de5fc-137">Формат для использования для сериализации значения для текста.</span><span class="sxs-lookup"><span data-stu-id="de5fc-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="de5fc-138">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="de5fc-138">Valid values are:</span></span><br><br><span data-ttu-id="de5fc-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="de5fc-139">- `string`.</span></span> <span data-ttu-id="de5fc-140">Значение сериализируется как строка с использованием <xref:System.ComponentModel.TypeConverter>.</span><span class="sxs-lookup"><span data-stu-id="de5fc-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="de5fc-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="de5fc-141">- `xml`.</span></span> <span data-ttu-id="de5fc-142">Значение сериализируется с помощью сериализации XML.</span><span class="sxs-lookup"><span data-stu-id="de5fc-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="de5fc-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="de5fc-143">- `binary`.</span></span> <span data-ttu-id="de5fc-144">Значение сериализируется как кодовое с помощью бинарного бинарного файла.</span><span class="sxs-lookup"><span data-stu-id="de5fc-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="de5fc-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="de5fc-145">- `custom`.</span></span> <span data-ttu-id="de5fc-146">Поставщик настроек обладает неотъемлемыми знаниями об этой настройке и сериализирует и десериализирует его.</span><span class="sxs-lookup"><span data-stu-id="de5fc-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="de5fc-147">\<значение> элемента</span><span class="sxs-lookup"><span data-stu-id="de5fc-147">\<value> element</span></span>

<span data-ttu-id="de5fc-148">Этот элемент содержит значение параметра.</span><span class="sxs-lookup"><span data-stu-id="de5fc-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="de5fc-149">Пример</span><span class="sxs-lookup"><span data-stu-id="de5fc-149">Example</span></span>

<span data-ttu-id="de5fc-150">В следующем примере показан файл параметров приложения, определяющий два параметра с областью применения и два пользовательских параметра:</span><span class="sxs-lookup"><span data-stu-id="de5fc-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
    </sectionGroup>
  </configSections>
  <applicationSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="Cursor" serializeAs="String">
        <value>Default</value>
      </setting>
      <setting name="DoubleBuffering" serializeAs="String">
        <value>False</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </applicationSettings>
  <userSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="FormTitle" serializeAs="String">
        <value>Form1</value>
      </setting>
      <setting name="FormSize" serializeAs="String">
        <value>595, 536</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </userSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="de5fc-151">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="de5fc-151">See also</span></span>

- [<span data-ttu-id="de5fc-152">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="de5fc-152">Application Settings Overview</span></span>](../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="de5fc-153">Архитектура параметров приложения</span><span class="sxs-lookup"><span data-stu-id="de5fc-153">Application Settings Architecture</span></span>](../../winforms/advanced/application-settings-architecture.md)
