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
# <a name="high-dpi-support-in-windows-forms"></a><span data-ttu-id="f8018-104">Поддержка высокого DPI в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8018-104">High DPI support in Windows Forms</span></span>

<span data-ttu-id="f8018-105">Начиная с .NET Framework 4,7 Windows Forms включает улучшения для распространенных сценариев высокого и динамического DPI.</span><span class="sxs-lookup"><span data-stu-id="f8018-105">Starting with the .NET Framework 4.7, Windows Forms includes enhancements for common high DPI and dynamic DPI scenarios.</span></span> <span data-ttu-id="f8018-106">Сюда входит следующее.</span><span class="sxs-lookup"><span data-stu-id="f8018-106">These include:</span></span>

- <span data-ttu-id="f8018-107">Улучшения в масштабировании и компоновке ряда элементов управления Windows Forms, таких как <xref:System.Windows.Forms.MonthCalendar> элемент управления и <xref:System.Windows.Forms.CheckedListBox> элемент управления.</span><span class="sxs-lookup"><span data-stu-id="f8018-107">Improvements in the scaling and layout of a number of Windows Forms controls, such as the <xref:System.Windows.Forms.MonthCalendar> control and the <xref:System.Windows.Forms.CheckedListBox> control.</span></span>

- <span data-ttu-id="f8018-108">Масштабирование с одним проходом.</span><span class="sxs-lookup"><span data-stu-id="f8018-108">Single-pass scaling.</span></span>  <span data-ttu-id="f8018-109">В .NET Framework 4,6 и более ранних версиях масштабирование выполнялось с помощью нескольких проходов, что привело к увеличению количества элементов управления, чем требовалось.</span><span class="sxs-lookup"><span data-stu-id="f8018-109">In the .NET Framework 4.6 and earlier versions, scaling was performed through multiple passes, which caused some controls to be scaled more than was necessary.</span></span>

- <span data-ttu-id="f8018-110">Поддержка сценариев динамического МАСШТАБИРОВАНИЯ, при которой пользователь изменяет значение DPI или коэффициент масштабирования после запуска Windows Forms приложения.</span><span class="sxs-lookup"><span data-stu-id="f8018-110">Support for dynamic DPI scenarios in which the user changes the DPI or scale factor after a Windows Forms application has been launched.</span></span>

<span data-ttu-id="f8018-111">В версиях .NET Framework, начиная с .NET Framework 4,7, расширенная поддержка высокого DPI является функцией согласия.</span><span class="sxs-lookup"><span data-stu-id="f8018-111">In versions of the .NET Framework starting with the .NET Framework 4.7, enhanced high DPI support is an opt-in feature.</span></span> <span data-ttu-id="f8018-112">Необходимо настроить приложение, чтобы воспользоваться его преимуществами.</span><span class="sxs-lookup"><span data-stu-id="f8018-112">You must configure your application to take advantage of it.</span></span>

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a><span data-ttu-id="f8018-113">Настройка приложения Windows Forms для поддержки высокого DPI</span><span class="sxs-lookup"><span data-stu-id="f8018-113">Configuring your Windows Forms app for high DPI support</span></span>

<span data-ttu-id="f8018-114">Новые функции Windows Forms, поддерживающие распознавание высокого DPI, доступны только в приложениях, предназначенных для .NET Framework 4,7 и запущенных в операционных системах Windows, начиная с обновления Windows 10 Creators Update.</span><span class="sxs-lookup"><span data-stu-id="f8018-114">The new Windows Forms features that support high DPI awareness are available only in applications that target the .NET Framework 4.7 and are running on Windows operating systems starting with the Windows 10 Creators Update.</span></span>

<span data-ttu-id="f8018-115">Кроме того, чтобы настроить поддержку высокого DPI в приложении Windows Forms, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f8018-115">In addition, to configure high DPI support in your Windows Forms application, you must do the following:</span></span>

- <span data-ttu-id="f8018-116">Объявление совместимости с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f8018-116">Declare compatibility with Windows 10.</span></span>

  <span data-ttu-id="f8018-117">Для этого добавьте в файл манифеста следующее:</span><span class="sxs-lookup"><span data-stu-id="f8018-117">To do this, add the following to your manifest file:</span></span>

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- <span data-ttu-id="f8018-118">Включение отслеживания DPI для каждого монитора в файле *app.config* .</span><span class="sxs-lookup"><span data-stu-id="f8018-118">Enable per-monitor DPI awareness in the *app.config* file.</span></span>

  <span data-ttu-id="f8018-119">Windows Forms появился новый [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) элемент для поддержки новых функций и настроек, добавленных начиная с .NET Framework 4,7.</span><span class="sxs-lookup"><span data-stu-id="f8018-119">Windows Forms introduces a new [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) element to support new features and customizations added starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="f8018-120">Чтобы воспользоваться преимуществами новых функций, поддерживающих высокое разрешение, добавьте в файл конфигурации приложения следующее:</span><span class="sxs-lookup"><span data-stu-id="f8018-120">To take advantage of the new features that support high DPI, add the following to your application configuration file.</span></span>

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>
  ```

  > [!IMPORTANT]
  > <span data-ttu-id="f8018-121">В предыдущих версиях .NET Framework использовался манифест для добавления поддержки высокого DPI.</span><span class="sxs-lookup"><span data-stu-id="f8018-121">In previous versions of the .NET Framework, you used the manifest to add high DPI support.</span></span> <span data-ttu-id="f8018-122">Этот подход больше не рекомендуется, так как он переопределяет параметры, определенные для файла app.config.</span><span class="sxs-lookup"><span data-stu-id="f8018-122">This approach is no longer recommended, since it overrides settings defined on the app.config file.</span></span>

- <span data-ttu-id="f8018-123">Вызовите статический <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="f8018-123">Call the static <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>

  <span data-ttu-id="f8018-124">Это должен быть первый вызов метода в точке входа приложения.</span><span class="sxs-lookup"><span data-stu-id="f8018-124">This should be the first method call in your application entry point.</span></span> <span data-ttu-id="f8018-125">Пример:</span><span class="sxs-lookup"><span data-stu-id="f8018-125">For example:</span></span>

  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a><span data-ttu-id="f8018-126">Отказ от отдельных функций высокого разрешения</span><span class="sxs-lookup"><span data-stu-id="f8018-126">Opting out of individual high DPI features</span></span>

<span data-ttu-id="f8018-127">Установка `DpiAwareness` значения `PerMonitorV2` включает все возможности поддержки высокого DPI, поддерживаемые .NET Framework версиями, начиная с .NET Framework 4,7.</span><span class="sxs-lookup"><span data-stu-id="f8018-127">Setting the `DpiAwareness` value to `PerMonitorV2` enables all high DPI awareness features supported by .NET Framework versions starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="f8018-128">Как правило, это подходит для большинства Windows Forms приложений.</span><span class="sxs-lookup"><span data-stu-id="f8018-128">Typically, this is adequate for most Windows Forms applications.</span></span> <span data-ttu-id="f8018-129">Однако вы можете отказаться от одной или нескольких отдельных функций.</span><span class="sxs-lookup"><span data-stu-id="f8018-129">However, you may want to opt out of one or more individual features.</span></span> <span data-ttu-id="f8018-130">Наиболее важной причиной этого является то, что существующий код приложения уже обрабатывает эту функцию.</span><span class="sxs-lookup"><span data-stu-id="f8018-130">The most important reason for doing this is that your existing application code already handles that feature.</span></span>  <span data-ttu-id="f8018-131">Например, если приложение обрабатывает автоматическое масштабирование, может потребоваться отключить функцию автоматического изменения размера следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f8018-131">For example, if your application handles auto scaling, you might want to disable the auto-resizing feature as follows:</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

<span data-ttu-id="f8018-132">Список отдельных ключей и их значений см. в разделе [Windows Forms Добавление элемента конфигурации](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span><span class="sxs-lookup"><span data-stu-id="f8018-132">For a list of individual keys and their values, see [Windows Forms Add Configuration Element](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span></span>

## <a name="new-dpi-change-events"></a><span data-ttu-id="f8018-133">Новые события изменения DPI</span><span class="sxs-lookup"><span data-stu-id="f8018-133">New DPI change events</span></span>

<span data-ttu-id="f8018-134">Начиная с .NET Framework 4,7, три новых события позволяют программно управлять изменениями динамического DPI:</span><span class="sxs-lookup"><span data-stu-id="f8018-134">Starting with the .NET Framework 4.7, three new events allow you to programmatically handle dynamic DPI changes:</span></span>

- <span data-ttu-id="f8018-135"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, которая возникает, когда значение DPI для элемента управления изменяется программным способом после события изменения DPI для родительского элемента управления или формы.</span><span class="sxs-lookup"><span data-stu-id="f8018-135"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, which is fired when the DPI setting for a control is changed programmatically after a DPI change event for it's parent control or form has occurred.</span></span>
- <span data-ttu-id="f8018-136"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, которая возникает, когда значение DPI для элемента управления изменяется программным способом до возникновения события изменения DPI для родительского элемента управления или формы.</span><span class="sxs-lookup"><span data-stu-id="f8018-136"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, which is fired when the DPI setting for a control is changed programmatically before a DPI change event for its parent control or form has occurred.</span></span>
- <span data-ttu-id="f8018-137"><xref:System.Windows.Forms.Form.DpiChanged>, которая возникает при изменении параметра DPI на устройстве отображения, на котором в данный момент отображается форма.</span><span class="sxs-lookup"><span data-stu-id="f8018-137"><xref:System.Windows.Forms.Form.DpiChanged>, which is fired when the DPI setting changes on the display device where the form is currently displayed.</span></span>

## <a name="new-helper-methods-and-properties"></a><span data-ttu-id="f8018-138">Новые вспомогательные методы и свойства</span><span class="sxs-lookup"><span data-stu-id="f8018-138">New helper methods and properties</span></span>

<span data-ttu-id="f8018-139">В .NET Framework 4,7 также добавляется ряд новых вспомогательных методов и свойств, которые предоставляют сведения о масштабировании DPI и позволяют выполнять масштабирование DPI.</span><span class="sxs-lookup"><span data-stu-id="f8018-139">The .NET Framework 4.7 also adds a number of new helper methods and properties that provide information about DPI scaling and allow you to perform DPI scaling.</span></span> <span data-ttu-id="f8018-140">Сюда входит следующее.</span><span class="sxs-lookup"><span data-stu-id="f8018-140">These include:</span></span>

- <span data-ttu-id="f8018-141"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, который преобразует значение из логического устройства в пиксел.</span><span class="sxs-lookup"><span data-stu-id="f8018-141"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, which converts a value from logical to device pixels.</span></span>

- <span data-ttu-id="f8018-142"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, который масштабирует растровое изображение на логическое значение DPI для устройства.</span><span class="sxs-lookup"><span data-stu-id="f8018-142"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, which scales a bitmap image to the logical DPI for a device.</span></span>

- <span data-ttu-id="f8018-143"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, который возвращает значение DPI для текущего устройства.</span><span class="sxs-lookup"><span data-stu-id="f8018-143"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, which returns the DPI for the current device.</span></span>

## <a name="versioning-considerations"></a><span data-ttu-id="f8018-144">Вопросы управления версиями</span><span class="sxs-lookup"><span data-stu-id="f8018-144">Versioning considerations</span></span>

<span data-ttu-id="f8018-145">В дополнение к работе на .NET Framework 4,7 и Windows 10 Creators Update, приложение также может работать в среде, в которой она несовместима с усовершенствованиями с высоким разрешением.</span><span class="sxs-lookup"><span data-stu-id="f8018-145">In addition to running on .NET Framework 4.7 and Windows 10 Creators Update, your application may also run in an environment in which it isn't compatible with high DPI improvements.</span></span> <span data-ttu-id="f8018-146">В этом случае вам потребуется разработать резервную копию приложения.</span><span class="sxs-lookup"><span data-stu-id="f8018-146">In this case, you'll need to develop a fallback for your application.</span></span> <span data-ttu-id="f8018-147">Это можно сделать для выполнения [пользовательского рисования](./controls/user-drawn-controls.md) с целью масштабирования.</span><span class="sxs-lookup"><span data-stu-id="f8018-147">You can do this to perform [custom drawing](./controls/user-drawn-controls.md) to handle scaling.</span></span>

<span data-ttu-id="f8018-148">Для этого необходимо также определить операционную систему, в которой выполняется приложение.</span><span class="sxs-lookup"><span data-stu-id="f8018-148">To do this, you also need to determine the operating system on which your app is running.</span></span> <span data-ttu-id="f8018-149">Это можно сделать с помощью кода, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f8018-149">You can do that with code like the following:</span></span>

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

<span data-ttu-id="f8018-150">Обратите внимание, что приложение не будет успешно обнаруживать Windows 10, если оно не было указано в качестве поддерживаемой операционной системы в манифесте приложения.</span><span class="sxs-lookup"><span data-stu-id="f8018-150">Note that your application won't successfully detect Windows 10 if it wasn't listed as a supported operating system in the application manifest.</span></span>

<span data-ttu-id="f8018-151">Также можно проверить версию .NET Framework, для которой было создано приложение.</span><span class="sxs-lookup"><span data-stu-id="f8018-151">You can also check the version of the .NET Framework that the application was built against:</span></span>

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a><span data-ttu-id="f8018-152">См. также</span><span class="sxs-lookup"><span data-stu-id="f8018-152">See also</span></span>

- [<span data-ttu-id="f8018-153">Windows Forms добавить элемент конфигурации</span><span class="sxs-lookup"><span data-stu-id="f8018-153">Windows Forms Add Configuration Element</span></span>](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [<span data-ttu-id="f8018-154">Настройка размера и масштаба формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8018-154">Adjusting the Size and Scale of Windows Forms</span></span>](adjusting-the-size-and-scale-of-windows-forms.md)
