---
title: Общие сведения о глобализации и локализации
description: Сведения о локализации и глобализации Windows Presentation Foundation, включая автоматический макет, вспомогательные сборки и локализованные атрибуты.
ms.date: 03/30/2017
helpviewer_keywords:
- globalization [WPF], about globalization
- localization [WPF], about localization
ms.assetid: 56e5a5c8-6c96-4d19-b8e1-a5be1dc564af
ms.openlocfilehash: 9a54ce2c265b989f99383ff9cdec961c80dd655c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168297"
---
# <a name="wpf-globalization-and-localization-overview"></a>Общие сведения о глобализации и локализации WPF

Если вы ограничиваете доступность продукта только на одном языке, вы ограничиваете потенциальную базу клиентов на часть населения в мире 7 500 000 000. Чтобы созданные приложения были доступны мировой аудитории, одним из лучших и наиболее экономичных способов охватить большее количество клиентов является экономически эффективная локализация продукта.

В этом обзоре рассматривается глобализация и локализация в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] . Глобализация — это проектирование и разработка приложений, которые выполняются в нескольких расположениях. Например, глобализация поддерживает локализованные пользовательские интерфейсы и региональные данные для пользователей на различных языках. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет глобализованные функции проектирования, включая автоматический макет, вспомогательные сборки, локализованные атрибуты и комментарии.

Локализация — это перевод ресурсов приложения в локализованные версии для конкретных языков и региональных параметров, которые поддерживает приложение. При локализации в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] вы используете API-интерфейсы в <xref:System.Windows.Markup.Localizer> пространстве имен. Эти API-интерфейсы. Пример средства командной строки для [средства LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml) . Сведения о том, как создать и использовать LocBaml, см. в разделе [Локализация приложения](how-to-localize-an-application.md).

## <a name="best-practices-for-globalization-and-localization-in-wpf"></a>Рекомендации по глобализации и локализации в WPF

Большинство возможностей глобализации и локализации, встроенных в, можно сделать, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] следуя советам по проектированию пользовательского интерфейса и локализации, которые предоставляет этот раздел.

### <a name="best-practices-for-wpf-ui-design"></a>Оптимальные методы разработки пользовательского интерфейса WPF

При проектировании [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] на основе рекомендуется [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] реализовать следующие рекомендации:

- Напишите [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , не создавайте [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] код. При создании [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] вы предоставляете его через встроенные API-интерфейсы локализации.

- Старайтесь не использовать абсолютные позиции и фиксированные размеры для размещения содержимого; Вместо этого используйте относительное или автоматическое изменение размера.

  - Используйте <xref:System.Windows.Window.SizeToContent%2A> и установите для ширины и высоты значение `Auto` .

  - Избегайте использования <xref:System.Windows.Controls.Canvas> для размещения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] s.

  - Используйте <xref:System.Windows.Controls.Grid> и его функцию совместного использования размера.

- Необходимо предусмотреть дополнительное пространство в полях, так как локализованный текст часто занимает больше места. Дополнительное пространство позволит использовать выступающие символы, возможно, присутствующие в конкретном языке.

- Включите <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> On <xref:System.Windows.Controls.TextBlock> , чтобы избежать обрезки.

- Задайте атрибут `xml:lang` . Этот атрибут описывает язык и региональные параметры определенного элемента и его дочерних элементов. Значение этого свойства изменяет поведение нескольких функций в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] . Например, изменяется процесс переноса по слогам, проверки орфографии, подстановки чисел, формирования сложных скриптов и подмены шрифта. Дополнительные сведения о настройке [обработки XML: lang в XAML](../../../desktop-wpf/xaml-services/xml-language-handling.md)см. в разделе [глобализация для WPF](globalization-for-wpf.md) .

- Создайте настраиваемый составной шрифт, чтобы улучшить управление шрифтами, используемыми для разных языков. По умолчанию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует шрифт глобалусеринтерфаце. Composite в каталоге Windows\Fonts..

- При создании приложений навигации, которые могут быть локализованы в языке и региональных параметрах, представляющих текст в формате справа налево, необходимо явно задать для <xref:System.Windows.FlowDirection> каждой страницы, чтобы страница не наследовалась <xref:System.Windows.FlowDirection> от класса <xref:System.Windows.Navigation.NavigationWindow> .

- При создании автономных приложений навигации, размещенных за пределами браузера, задайте <xref:System.Windows.Application.StartupUri%2A> для начального приложения <xref:System.Windows.Navigation.NavigationWindow> вместо страницы (например, `<Application StartupUri="NavigationWindow.xaml">` ). Такая схема позволяет изменять <xref:System.Windows.FlowDirection> окно и панель навигации. Дополнительные сведения и пример см. в разделе [Пример домашней страницы глобализации](https://github.com/microsoft/WPF-Samples/tree/master/Globalization%20and%20Localization/GlobalizationHomepage).

### <a name="best-practices-for-wpf-localization"></a>Оптимальные методы локализации приложений WPF

При локализации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложений на основе рекомендуется реализовать следующие рекомендации:

- Используйте комментарии локализации, чтобы предоставить дополнительный контекст для локализаторов.

- Используйте атрибуты локализации для управления локализацией вместо выборочного пропуска <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> свойств элементов. Дополнительные сведения см. в статье [атрибуты и комментарии локализации](localization-attributes-and-comments.md) .

- Используйте `msbuild -t:updateuid` и `-t:checkuid` для добавления и проверки <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> свойств в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Используйте <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> свойства для контроля изменений между разработкой и локализацией. <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>свойства помогают локализовать новые изменения в разработке. Если вручную добавить <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> свойства в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , задача обычно утомительна и менее точная.

  - Не изменяйте и не изменяйте <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> свойства после начала локализации.

  - Не используйте дублирующиеся <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Свойства (Помните, что этот Совет следует использовать при использовании команды копирования и вставки).

  - Задайте `UltimateResourceFallback` расположение в AssemblyInfo., \* чтобы указать соответствующий язык для отката (например, `[assembly: NeutralResourcesLanguage("en-US",   UltimateResourceFallbackLocation.Satellite)]` ).

    Если вы решили включить исходный язык в основную сборку, опустив `<UICulture>` тег в файле проекта, задайте `UltimateResourceFallback` расположение в качестве основной сборки, а не вспомогательной (например, `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.MainAssembly)]` ).

## <a name="localize-a-wpf-application"></a>Локализация приложения WPF

При локализации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения у вас есть несколько вариантов. Например, можно привязать локализуемые ресурсы в приложении к XML-файлу, сохранить локализуемый текст в таблицах RESX или использовать [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файлы локализатора. В этом разделе описывается рабочий процесс локализации, в котором используется форма BAML языка XAML, которая предоставляет несколько преимуществ.

- Вы можете локализовать после сборки.

- Можно выполнить обновление до более новой версии формы BAML XAML с локализацией из старой версии XAML-формы, чтобы можно было локализовать в то же время, в котором вы разрабатываете.

- Можно проверить исходные элементы и семантику во время компиляции, поскольку формат BAML XAML является скомпилированной формой [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .

### <a name="localization-build-process"></a>Процесс построения локализации

При разработке [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения процесс сборки для локализации выглядит следующим образом:

- Разработчик создает и глобализация [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения. В файле проекта разработчик устанавливает, `<UICulture>en-US</UICulture>` что при компиляции приложения создается основная сборка, не зависящая от языка. Эта сборка имеет вспомогательный файл .resources.dll, содержащий все локализуемые ресурсы. При необходимости можно разместить исходный язык в основной сборке, так как наши API-интерфейсы локализации поддерживают извлечение из основной сборки.

- При компиляции файла в сборку [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] преобразуется в форму BAML XAML. Язык и региональные стандарты, `MyDialog.exe` зависящие от культуры (на английском языке) `MyDialog.resources.dll` , выводятся на английском языке.

### <a name="localization-workflow"></a>Рабочий процесс локализации

Процесс локализации начинается после сборки нелокализованного `MyDialog.resources.dll` файла. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]Элементы и свойства в исходном коде [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] извлекаются из формы BAML XAML в пары "ключ-значение" с помощью API в разделе <xref:System.Windows.Markup.Localizer> . Локализаторы используют пары "ключ —значение" для локализации приложения. После завершения локализации можно создать файл .resource.dll на основе новых значений.

Ключи пар «ключ-значение» — это `x:Uid` значения, помещаемые разработчиком в исходном виде [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Эти `x:Uid` значения позволяют API отслеживанию и слиянию изменений, происходящих между разработчиком и локализаторам во время локализации. Например, если разработчик изменяет [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] после начала локализации, можно объединить изменение в разработку с уже завершенной работой по локализации, чтобы при этом было потеряно минимальное количество операций перевода.

На приведенном ниже рисунке показан типичный рабочий процесс локализации на основе BAML-формы XAML. На этой схеме предполагается, что разработчик пишет приложение на английском языке. Разработчик создает и глобализует приложение WPF. В файле проекта разработчик устанавливает, `<UICulture>en-US</UICulture>` что при сборке не зависящая от языка основная сборка создается с помощью вспомогательной .resources.dll, содержащей все локализуемые ресурсы. Кроме того, можно сохранить исходный язык в основной сборке, так как интерфейсы API локализации WPF поддерживают извлечение из основной сборки. По завершении процесса сборки XAML компилируется в BAML. Независимый от языка и региональных параметров файл MyDialog.exe.resources.dll поставляется англоязычному пользователю.

![Схема, показывающая рабочий процесс локализации.](./media/wpf-globalization-and-localization-overview/localization-workflow.png)

![Схема, на которой показан нелокализованный рабочий процесс.](./media/wpf-globalization-and-localization-overview/unlocalized-workflow.png)

## <a name="examples-of-wpf-localization"></a>Примеры локализации WPF

В этом разделе содержатся примеры локализованных приложений, которые помогут вам понять, как создавать и локализовать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения.

### <a name="run-dialog-box-example"></a>Пример диалогового окна "Выполнить"

На следующих рисунках показаны выходные данные образца диалогового окна **выполнить** .

**английский:**

![Снимок экрана, показывающий диалоговое окно запуска на английском языке.](./media/wpf-globalization-and-localization-overview/run-dialog-box-english.png)

**немецкий:**

![Снимок экрана, показывающий диалоговое окно запуска на немецком языке.](./media/wpf-globalization-and-localization-overview/run-dialog-box-german.png)

**Разработка глобального диалогового окна "Выполнить"**

В этом примере создается диалоговое окно **выполнить** с помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Это диалоговое окно эквивалентно диалоговому окну **выполнить** , которое доступно из меню "Пуск" Microsoft Windows.

Некоторые замечания по созданию глобальных диалоговых окон

**Автоматический макет**

*В файле Window1.xaml*

`<Window SizeToContent="WidthAndHeight">`

Предыдущее свойство Window автоматически изменяет размер окна в соответствии с размером содержимого. Это свойство предотвращает обрезание содержимого окна, которое увеличивается в размере после локализации. Кроме того, оно также удаляет лишнее пространство, если содержимое уменьшается в размерах после локализации.

`<Grid x:Uid="Grid_1">`

<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] правильной работы API локализации требуются свойства.

Они используются [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API локализации для контроля изменений между разработкой и локализацией [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] . <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>свойства позволяют выполнить слияние более новой версии [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] с более старой локализацией [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] . Чтобы добавить <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> свойство, запустите `msbuild -t:updateuid RunDialog.csproj` в командной оболочке. Это рекомендуемый метод добавления свойств, <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> поскольку их добавление вручную обычно занимает много времени и менее точно. Чтобы проверить, <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> правильно ли установлены свойства, запустите `msbuild -t:checkuid RunDialog.csproj` .

[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]Структурирован с помощью <xref:System.Windows.Controls.Grid> элемента управления, который является полезным элементом управления для использования преимуществ автоматического макета в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] . Обратите внимание, что диалоговое окно разделено на три строки и пять столбцов. Не одно из определений строк и столбцов имеет фиксированный размер. Таким образом, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементы, расположенные в каждой ячейке, могут адаптироваться к увеличению и уменьшению размера во время локализации.

[!code-xaml[GlobalizationRunDialog#GridColumnDef](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef)]

Первые два столбца, в которых размещены метки **Open:** и <xref:System.Windows.Controls.ComboBox> , используют 10 процентов от [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] общей ширины.

[!code-xaml[GlobalizationRunDialog#GridColumnDef2](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef2)]

Обратите внимание, что в примере используется функция общего изменения размера <xref:System.Windows.Controls.Grid> . Последние три столбца используют преимущества этого метода, помещая себя в один и тот же <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> . Как следует из имени свойства, это позволяет столбцам использовать один и тот же размер. Итак, когда «Browse...» локализовано для более длинной строки "Durchsuchen...", все кнопки увеличиваются по ширине вместо небольшой кнопки "ОК" и непропорционального большого размера "Durchsuchen..." переключатель.

**XML: lang**

`xml:lang="en-US"`

Обратите внимание на [обработку XML: lang в XAML](../../../desktop-wpf/xaml-services/xml-language-handling.md) , помещенную в корневой элемент [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] . Это свойство описывает язык и региональные параметры конкретного элемента и его потомков. Это значение используется несколькими компонентами в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и должно быть соответствующим образом изменено во время локализации. Это значение изменяется в зависимости от того, какой языковой словарь используется для расстановки переносов и проверки орфографии слов. Оно также влияет на отображение цифр и на то, как система подмены шрифтов выбирает шрифт для использования. Наконец, это свойство влияет на способ отображения чисел и на способ написания текста в сложных скриптах. По умолчанию используется значение en-US.

**Создание вспомогательной сборки ресурсов**

*В файле .csproj*

Измените `.csproj` файл и добавьте следующий тег в безусловную `<PropertyGroup>` :

`<UICulture>en-US</UICulture>`

Обратите внимание на добавление `UICulture` значения. Если для этого параметра задано допустимое <xref:System.Globalization.CultureInfo> значение, например en-US, сборка проекта создаст вспомогательную сборку со всеми локализованными ресурсами.

`<Resource Include="RunIcon.JPG">`

`<Localizable>False</Localizable>`

`</Resource>`

`RunIcon.JPG`Локализация не требуется, так как она должна отображаться одинаково для всех языков и региональных параметров. `Localizable`имеет значение, чтобы `false` оно оставалось в независимой от языка основной сборке, а не в вспомогательной сборке. Значение по умолчанию для всех некомпилируемых ресурсов равно `Localizable` `true` .

**Локализация диалогового окна "Выполнить"**

**Анализ**

После сборки приложения первым шагом в локализации является анализ локализуемых ресурсов из вспомогательной сборки. Для целей этого раздела используйте образец средства LocBaml, который можно найти в [примере средства LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml). Обратите внимание, что LocBaml ― только демонстрационное средство, предназначенное помочь начать работу по созданию средства локализации, встраиваемого в процесс локализации. С помощью LocBaml выполните следующую команду, чтобы выполнить синтаксический анализ: **LocBaml/парсе RunDialog.resources.dll/out:** для создания файла "RunDialog.resources.dll.CSV".

**Localize**

Для редактирования этого файла можно воспользоваться любым редактором CSV, поддерживающим Юникод. Исключите все записи с категорией локализации "Нет". Должны остаться следующие записи.

|Ключ ресурса|Категория локализации|Значение|
|-|-|-|
|Button_1:System.Windows.Controls.Button.$Content|Кнопка|OK|
|Button_2:System.Windows.Controls.Button.$Content|Кнопка|Отменить|
|Button_3:System.Windows.Controls.Button.$Content|Кнопка|Обзор...|
|ComboBox_1:System.Windows.Controls.ComboBox.$Content|ComboBox||
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Text|Введите имя программы, папки, документа или ресурса Интернета, и Windows откроет их.|
|TextBlock_2:System.Windows.Controls.TextBlock.$Content|Text|Открыто:|
|Window_1:System.Windows.Window.Title|Заголовок|Выполнить|

Для локализации приложений в немецком языке потребуются следующие переводы.

|Ключ ресурса|Категория локализации|Значение|
|-|-|-|
|Button_1:System.Windows.Controls.Button.$Content|Кнопка|OK|
|Button_2:System.Windows.Controls.Button.$Content|Кнопка|Abbrechen|
|Button_3:System.Windows.Controls.Button.$Content|Кнопка|Durchsuchen…|
|ComboBox_1:System.Windows.Controls.ComboBox.$Content|ComboBox||
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Text|Geben Sie den Namen eines Programms, Ordners, Dokuments oder einer Internetresource an.|
|TextBlock_2:System.Windows.Controls.TextBlock.$Content|Text|Открыть.|
|Window_1:System.Windows.Window.Title|Заголовок|Выполнить|

**Generate**

Последний шаг локализации включает создание только что локализованной вспомогательной сборки. Эту задачу можно решить с помощью следующей команды LocBaml.

**LocBaml.exe /generate RunDialog.resources.dll /trans:RunDialog.resources.dll.CSV /out: . /cul:de-DE**

В Windows на немецком языке, если эта resources.dll помещается в папку de-DE рядом с основной сборкой, этот ресурс будет автоматически загружаться, а не в папку en-US. Если у вас нет немецкой версии Windows для тестирования, задайте для языка и региональных параметров используемые вами язык и региональные параметры Windows (например, `en-US` ), а затем замените исходную библиотеку ресурсов.

**Загрузка вспомогательных ресурсов**

|MyDialog.exe|en-US\MyDialog.resources.dll|de-DE\MyDialog.resources.dll|
|------------------|------------------------------------|------------------------------------|
|Код|Исходный английский BAML|Локализованный BAML|
|Ресурсы, не зависящие от языка и региональных параметров|Другие ресурсы на английском языке|Другие ресурсы, локализованные для немецкого языка|

.NET автоматически выбирает сборку вспомогательных ресурсов для загрузки в зависимости от приложения <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> . По умолчанию используется язык и региональные параметры операционной системы Windows. Если вы используете Windows на немецком языке, файл *de-DE\MyDialog.resources.dll* загружается. Если вы используете Windows на английском языке, файл *en-US\MyDialog.resources.dll* загружается. Для приложения можно задать конечный резервный ресурс, указав `NeutralResourcesLanguage` атрибут в файле *AssemblyInfo* проекта. Например, если указать:

`[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.Satellite)]`

Затем файл *en-US\MyDialog.resources.dll* используется с Windows на немецком языке, если ни один из следующих файлов не доступен: *de-DE\MyDialog.resources.dll* или *de\MyDialog.resources.dll*.

### <a name="microsoft-saudi-arabia-homepage"></a>Домашняя страница сайта Майкрософт для Саудовской Аравии

На рисунке ниже показаны английская и арабская домашние страницы. Полный пример, в котором создаются эти графические элементы, см. в разделе [Пример домашней страницы глобализации](https://github.com/microsoft/WPF-Samples/tree/master/Globalization%20and%20Localization/GlobalizationHomepage).

**английский:**

![Снимок экрана, на котором показана домашняя страница английского языка.](./media/wpf-globalization-and-localization-overview/english-home-page-sample.jpg)

**арабский:**

![Снимок экрана, показывающий домашнюю страницу для арабского языка.](./media/wpf-globalization-and-localization-overview/arabic-home-page-sample.jpg)

### <a name="designing-a-global-microsoft-home-page"></a>Разработка глобальной домашней страницы Майкрософт

Этот макет веб-сайта Майкрософт для Саудовской Аравии показывает функциональные возможности глобализации, предоставляемые для языков с порядком чтения справа налево (RightToLeft). Такие языки, как иврит и арабский, имеют порядок чтения справа налево, поэтому компоновка [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] должна быть размещена совершенно иначе, чем в языках с направлением письма слева направо, например на английском языке. Локализация с языка с направлением письма слева направо на язык с направлением письма справа налево или наоборот может быть достаточно сложной. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] разработан так, чтобы значительно упростить подобные локализации.

**FlowDirection**

*Homepage.xaml:*

[!code-xaml[GlobalizationHomepage#Homepage](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#homepage)]

Обратите внимание на <xref:System.Windows.FrameworkElement.FlowDirection%2A> свойство в <xref:System.Windows.Controls.Page> . Изменение этого свойства на <xref:System.Windows.FlowDirection.RightToLeft> изменит свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A> <xref:System.Windows.Controls.Page> и его дочерние элементы таким образом, чтобы макет этого элемента [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] перестал быть справа налево, как и хотелось бы для арабского пользователя. Один из них может переопределить поведение наследования, указав явный <xref:System.Windows.FrameworkElement.FlowDirection%2A> для любого элемента. <xref:System.Windows.FrameworkElement.FlowDirection%2A>Свойство доступно в любом элементе, <xref:System.Windows.FrameworkElement> связанном с документом, и имеет неявное значение <xref:System.Windows.FlowDirection.LeftToRight> .

Обратите внимание, что даже фоновые градиентные кисти перевернуты правильно при <xref:System.Windows.FrameworkElement.FlowDirection%2A> изменении корня:

**FlowDirection="LeftToRight"**

![Снимок экрана, показывающий поток градиента слева направо.](./media/wpf-globalization-and-localization-overview/gradient-flow-left-right.png)

**FlowDirection="RightToLeft"**

![Снимок экрана, показывающий поток градиента справа налево.](./media/wpf-globalization-and-localization-overview/gradient-flow-right-left.png)

**Избегайте использования фиксированных размеров для панелей и элементов управления**

Взгляните на homepage. XAML, обратите внимание на то, что помимо фиксированной ширины и высоты, заданной для всей [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] верхней части <xref:System.Windows.Controls.DockPanel> , нет других фиксированных измерений. Не следует использовать фиксированные размеры, чтобы предотвратить отсечение локализованного текста, который может быть больше, чем исходный текст. Панели и элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] будут автоматически изменяться в размерах в зависимости от находящегося в них содержимого. Большинство элементов управления также имеют минимальные и максимальные размеры, которые можно задать для большего контроля (например, MinWidth = "20"). С помощью <xref:System.Windows.Controls.Grid> можно также задать относительную ширину и высоту, используя " \* " (например, `Width="0.25*"` ) или функцию совместного использования размера ячейки.

**Комментарии о локализации**

Во многих случаях содержимое может быть неоднозначным и трудным для перевода. Разработчик и проектировщик имеют возможность предоставить локализаторам дополнительный контекст и примечания в комментариях локализации. Например, в приведенных ниже комментариях локализации приводится разъяснение использования символа "&#124;".

[!code-xaml[GlobalizationHomepage#LocalizationComment](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcomment)]

Этот комментарий связан с содержимым TextBlock_1 и в случае средства LocBaml (см. раздел [Локализация приложения](how-to-localize-an-application.md)) оно может отображаться в шестом столбце строки TextBlock_1 в файле Output. csv.

|Ключ ресурса|Категория|Доступен для чтения|Изменяемый|Комментарий|Значение|
|-|-|-|-|-|-|
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Text|TRUE|TRUE|Этот символ используется в качестве декоративного правила.|&#124;|

Комментарии могут быть помещены в содержимое или в свойство любого элемента посредством следующего синтаксиса.

[!code-xaml[GlobalizationHomepage#LocalizationCommentsProp](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcommentsprop)]

**Атрибуты локализации**

Разработчику или менеджеру локализации часто бывает необходимо управлять тем, что локализаторы могут читать и изменять. Например, может быть нежелательно, чтобы локализатор переводил название компании или юридическую формулировку. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет атрибуты, позволяющие задать удобочитаемость, изменяемость и категорию содержимого элемента или свойства, которые средство локализации может использовать для блокировки, скрытия или сортировки элементов. Для получения дополнительной информации см. <xref:System.Windows.Localization.Attributes%2A>. В этом примере средство LocBaml только выводит значения этих атрибутов. Во всех элементах управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] эти атрибуты имеют значения по умолчанию, но их можно переопределять. Например, в следующем примере переопределяются атрибуты локализации по умолчанию для `TextBlock_1` и задается, что содержимое будет доступно для чтения, но не может быть изменено для локализаторов.

[!code-xaml[LocalizationComAtt#LocalizationAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributes)]

Помимо атрибутов чтения и изменения, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет перечисление общих категорий пользовательского интерфейса ( <xref:System.Windows.LocalizationCategory> ), которые можно использовать для предоставления локализаторам большего контекста. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Категории по умолчанию для элементов управления платформы можно также переопределить в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .

[!code-xaml[LocalizationComAtt#LocalizationAttributesOverridden](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributesoverridden)]

Атрибуты локализации по умолчанию, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляемые, можно также переопределять с помощью кода, поэтому можно правильно задать значения по умолчанию для пользовательских элементов управления. Пример:

```csharp
[Localizability(Readability = Readability.Readable, Modifiability=Modifiability.Unmodifiable, LocalizationCategory.None)]
public class CorporateLogo : TextBlock
{
    // ...
}
```

Атрибуты каждого экземпляра, заданные в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , будут иметь приоритет над значениями, заданными в коде для пользовательских элементов управления. Дополнительные сведения об атрибутах и комментариях см. в разделе [атрибуты и комментарии локализации](localization-attributes-and-comments.md).

**Подмена шрифтов и составные шрифты**

Если указать шрифт, который не поддерживает заданный диапазон codepoint, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] автоматически вернется к нему, который выполняется с помощью глобального пользовательского интерфейса. компоситефонт, расположенного в каталоге Windows\Fonts.. Составные шрифты работают так же, как любой другой шрифт, и могут использоваться явно путем установки элемента `FontFamily` (например, `FontFamily="Global User Interface"` ). Вы можете задавать собственные предпочтения для подмены шрифта путем создания собственного составного шрифта и указания его использования для конкретных языков и диапазонов кодовых точек.

Дополнительные сведения о составных шрифтах см. в разделе <xref:System.Windows.Media.FontFamily> .

**Локализация домашней страницы Майкрософт**

Для локализации этого приложения можно выполнить те же действия, что и в примере локализации диалогового окна "Выполнить". Локализованный CSV-файл для арабского языка доступен в [образце домашней страницы глобализации](https://github.com/microsoft/WPF-Samples/tree/master/Globalization%20and%20Localization/GlobalizationHomepage).
