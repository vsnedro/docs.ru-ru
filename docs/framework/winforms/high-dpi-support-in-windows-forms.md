---
title: Поддержка высокого разрешения
description: Узнайте о поддержке в Windows Forms для распространенных сценариев высокого и динамического DPI. Также Узнайте, как настроить приложения Windows Forms для поддержки высокого DPI.
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
ms.openlocfilehash: a9e0766307095da447c772de5a3065c18b7b7154
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325652"
---
# <a name="high-dpi-support-in-windows-forms"></a>Поддержка высокого DPI в Windows Forms

Начиная с .NET Framework 4,7 Windows Forms включает улучшения для распространенных сценариев высокого и динамического DPI. Сюда входит следующее.

- Улучшения в масштабировании и компоновке ряда элементов управления Windows Forms, таких как <xref:System.Windows.Forms.MonthCalendar> элемент управления и <xref:System.Windows.Forms.CheckedListBox> элемент управления.

- Масштабирование с одним проходом.  В .NET Framework 4,6 и более ранних версиях масштабирование выполнялось с помощью нескольких проходов, что привело к увеличению количества элементов управления, чем требовалось.

- Поддержка сценариев динамического МАСШТАБИРОВАНИЯ, при которой пользователь изменяет значение DPI или коэффициент масштабирования после запуска Windows Forms приложения.

В версиях .NET Framework, начиная с .NET Framework 4,7, расширенная поддержка высокого DPI является функцией согласия. Необходимо настроить приложение, чтобы воспользоваться его преимуществами.

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a>Настройка приложения Windows Forms для поддержки высокого DPI

Новые функции Windows Forms, поддерживающие распознавание высокого DPI, доступны только в приложениях, предназначенных для .NET Framework 4,7 и запущенных в операционных системах Windows, начиная с обновления Windows 10 Creators Update.

Кроме того, чтобы настроить поддержку высокого DPI в приложении Windows Forms, необходимо выполнить следующие действия.

- Объявление совместимости с Windows 10.

  Для этого добавьте в файл манифеста следующее:

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- Включение отслеживания DPI для каждого монитора в файле *app.config* .

  Windows Forms появился новый [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) элемент для поддержки новых функций и настроек, добавленных начиная с .NET Framework 4,7. Чтобы воспользоваться преимуществами новых функций, поддерживающих высокое разрешение, добавьте в файл конфигурации приложения следующее:

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>
  ```

  > [!IMPORTANT]
  > В предыдущих версиях .NET Framework использовался манифест для добавления поддержки высокого DPI. Этот подход больше не рекомендуется, так как он переопределяет параметры, определенные для файла app.config.

- Вызовите статический <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> метод.

  Это должен быть первый вызов метода в точке входа приложения. Пример:

  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a>Отказ от отдельных функций высокого разрешения

Установка `DpiAwareness` значения `PerMonitorV2` включает все возможности поддержки высокого DPI, поддерживаемые .NET Framework версиями, начиная с .NET Framework 4,7. Как правило, это подходит для большинства Windows Forms приложений. Однако вы можете отказаться от одной или нескольких отдельных функций. Наиболее важной причиной этого является то, что существующий код приложения уже обрабатывает эту функцию.  Например, если приложение обрабатывает автоматическое масштабирование, может потребоваться отключить функцию автоматического изменения размера следующим образом:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

Список отдельных ключей и их значений см. в разделе [Windows Forms Добавление элемента конфигурации](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).

## <a name="new-dpi-change-events"></a>Новые события изменения DPI

Начиная с .NET Framework 4,7, три новых события позволяют программно управлять изменениями динамического DPI:

- <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, которая возникает, когда значение DPI для элемента управления изменяется программным способом после события изменения DPI для родительского элемента управления или формы.
- <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, которая возникает, когда значение DPI для элемента управления изменяется программным способом до возникновения события изменения DPI для родительского элемента управления или формы.
- <xref:System.Windows.Forms.Form.DpiChanged>, которая возникает при изменении параметра DPI на устройстве отображения, на котором в данный момент отображается форма.

## <a name="new-helper-methods-and-properties"></a>Новые вспомогательные методы и свойства

В .NET Framework 4,7 также добавляется ряд новых вспомогательных методов и свойств, которые предоставляют сведения о масштабировании DPI и позволяют выполнять масштабирование DPI. Сюда входит следующее.

- <xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, который преобразует значение из логического устройства в пиксел.

- <xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, который масштабирует растровое изображение на логическое значение DPI для устройства.

- <xref:System.Windows.Forms.Control.DeviceDpi%2A>, который возвращает значение DPI для текущего устройства.

## <a name="versioning-considerations"></a>Вопросы управления версиями

В дополнение к работе на .NET Framework 4,7 и Windows 10 Creators Update, приложение также может работать в среде, в которой она несовместима с усовершенствованиями с высоким разрешением. В этом случае вам потребуется разработать резервную копию приложения. Это можно сделать для выполнения [пользовательского рисования](./controls/user-drawn-controls.md) с целью масштабирования.

Для этого необходимо также определить операционную систему, в которой выполняется приложение. Это можно сделать с помощью кода, как в следующем примере:

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

Обратите внимание, что приложение не будет успешно обнаруживать Windows 10, если оно не было указано в качестве поддерживаемой операционной системы в манифесте приложения.

Также можно проверить версию .NET Framework, для которой было создано приложение.

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a>См. также

- [Windows Forms добавить элемент конфигурации](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [Настройка размера и масштаба формы Windows Forms](adjusting-the-size-and-scale-of-windows-forms.md)
