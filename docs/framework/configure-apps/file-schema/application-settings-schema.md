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
# <a name="application-settings-schema"></a>Схема настройки приложений

Настройки приложений позволяют приложению Windows Forms или ASP.NET для хранения и извлечения параметров, с тем чтобы с развернуть приложения и пользовательские настройки. В этом контексте *параметр* представляет собой любую информацию, которая может быть специфична для приложения или специфична для текущего пользователя - от строки подключения базы данных до предпочтительного размера окна по умолчанию пользователя.

По умолчанию настройки приложения в приложении Windows Forms используют <xref:System.Configuration.LocalFileSettingsProvider> класс, который использует систему конфигурации .NET для хранения настроек в файле конфигурации XML. Для получения дополнительной информации о файлах, используемых настройками приложений, [см.](../../winforms/advanced/application-settings-architecture.md)

Настройки приложения определяют следующие элементы как часть используемых файлов конфигурации.

| Элемент                    | Описание                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings>** | Содержит все ** \<настройки>** теги, специфичные для приложения.                         |
| **\<userSettings>**        | Содержит все ** \<настройки>** теги, специфичные для текущего пользователя.                        |
| **\<установка>**             | Определяет параметр. Ребенок либо ** \<>приложений, либо** ** \<>userSettings. ** |
| **\<значение>**               | Определяет значение параметра. Ребенок ** \<установки>**.                                   |

## <a name="applicationsettings-element"></a>\<applicationSettings> элемент

Этот элемент содержит все ** \<настройки>** теги, которые являются специфическими для экземпляра приложения на клиентском компьютере. Атрибуты не определяются.

## <a name="usersettings-element"></a>\<userSettings> элемент

Этот элемент содержит все ** \<настройки>** теги, которые являются специфическими для пользователя, который в настоящее время использует приложение. Атрибуты не определяются.

## <a name="setting-element"></a>\<установка элемента>

Этот элемент определяет настройки. Он имеет следующие атрибуты.

| Атрибут        | Описание |
| ---------------- | ----------- |
| **name**         | Обязательный элемент. Уникальный идентификатор настройки. Настройки, созданные через Visual `ProjectName.Properties.Settings`Studio, сохраняются с именем. |
| **serializeAs** | Обязательный элемент. Формат для использования для сериализации значения для текста. Допустимые значения:<br><br>- `string`. Значение сериализируется как строка с использованием <xref:System.ComponentModel.TypeConverter>.<br>- `xml`. Значение сериализируется с помощью сериализации XML.<br>- `binary`. Значение сериализируется как кодовое с помощью бинарного бинарного файла.<br />- `custom`. Поставщик настроек обладает неотъемлемыми знаниями об этой настройке и сериализирует и десериализирует его. |

## <a name="value-element"></a>\<значение> элемента

Этот элемент содержит значение параметра.

## <a name="example"></a>Пример

В следующем примере показан файл параметров приложения, определяющий два параметра с областью применения и два пользовательских параметра:

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

## <a name="see-also"></a>См. также раздел

- [Общие сведения о параметрах приложений](../../winforms/advanced/application-settings-overview.md)
- [Архитектура параметров приложения](../../winforms/advanced/application-settings-architecture.md)
