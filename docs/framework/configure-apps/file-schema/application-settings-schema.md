---
title: Схема параметров приложения
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: fc9cd8ac3819c6a02019c871e7bd45ceb4c2cef7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552314"
---
# <a name="application-settings-schema"></a>Схема параметров приложения

Параметры приложения позволяют Windows Forms или ASP.NET приложению сохранять и извлекать параметры приложения и области пользователя. В этом контексте *параметр* — это любой фрагмент информации, который может быть специфичен для приложения или зависит от текущего пользователя — от строки подключения к базе данных до предпочитаемого пользователем размера окна по умолчанию.

По умолчанию параметры приложения в Windows Formsном приложении используют <xref:System.Configuration.LocalFileSettingsProvider> класс, который использует систему конфигурации .NET для хранения параметров в XML-файле конфигурации. Дополнительные сведения о файлах, используемых параметрами приложения, см. в разделе [архитектура параметров приложения](/dotnet/desktop/winforms/advanced/application-settings-architecture).

Параметры приложения определяют следующие элементы в составе файлов конфигурации, которые он использует.

| Элемент                    | Описание                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings>** | Содержит все **\<setting>** теги, характерные для приложения.                         |
| **\<userSettings>**        | Содержит все **\<setting>** теги, относящиеся к текущему пользователю.                        |
| **\<setting>**             | Определяет параметр. Дочерний элемент либо **\<applicationSettings>** или **\<userSettings>** . |
| **\<value>**               | Определяет значение параметра. Дочерний элемент **\<setting>** .                                   |

## <a name="applicationsettings-element"></a>Элемент \<applicationSettings>

Этот элемент содержит все **\<setting>** теги, характерные для экземпляра приложения на клиентском компьютере. Атрибуты не определяются.

## <a name="usersettings-element"></a>Элемент \<userSettings>

Этот элемент содержит все **\<setting>** теги, характерные для пользователя, который в настоящее время использует приложение. Атрибуты не определяются.

## <a name="setting-element"></a>\<setting> - элемент

Этот элемент определяет параметр. Он имеет следующие атрибуты.

| attribute        | Описание |
| ---------------- | ----------- |
| **name**         | Обязательный элемент. Уникальный идентификатор параметра. Параметры, созданные в Visual Studio, сохраняются с именем `ProjectName.Properties.Settings` . |
| **serializeAs** | Обязательный. Формат, используемый для сериализации значения в текст. Допустимые значения:<br><br>- `string`. Значение сериализуется в виде строки с помощью <xref:System.ComponentModel.TypeConverter> .<br>- `xml`. Значение сериализуется с помощью сериализации XML.<br>- `binary`. Значение сериализуется как двоичный файл, закодированный в виде текста, с помощью двоичной сериализации.<br />- `custom`. Поставщик параметров обладает знаниями об этом параметре и сериализует и десериализует его. |

## <a name="value-element"></a>Элемент \<value>

Этот элемент содержит значение параметра.

## <a name="example"></a>Пример

В следующем примере показан файл параметров приложения, который определяет два параметра области приложения и два параметра уровня пользователя:

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

## <a name="see-also"></a>См. также

- [Общие сведения о параметрах приложений](/dotnet/desktop/winforms/advanced/application-settings-overview)
- [Архитектура параметров приложения](/dotnet/desktop/winforms/advanced/application-settings-architecture)
