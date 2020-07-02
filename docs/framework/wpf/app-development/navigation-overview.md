---
title: Общие сведения о переходах
description: Сведения о поддержке навигации в стиле браузера, используемой в автономных приложениях и приложениях браузера XAML в Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loose XAML files [WPF]
- windows [WPF]
- Start page [WPF]
- HTML files [WPF]
- structured navigation [WPF]
- fragment navigation [WPF]
- URIs (Uniform Resource Identifiers)
- custom objects [WPF]
- Uniform Resource Identifiers (URIs)
- pages [WPF]
- frames [WPF]
- navigation hosts [WPF]
- journals [WPF]
- lifetimes [WPF]
- retaining content state [WPF]
- content state [WPF]
- programmatic navigation [WPF]
- hyperlinks [WPF]
ms.assetid: 86ad2143-606a-4e34-bf7e-51a2594248b8
ms.openlocfilehash: 2aac1b3a38b6240bfba1b90983fd9cbd18b31b6f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621708"
---
# <a name="navigation-overview"></a>Общие сведения о переходах

Windows Presentation Foundation (WPF) поддерживает навигацию в стиле браузера, которую можно использовать в приложениях двух типов: автономные приложения и приложения браузера XAML (XBAP). Чтобы упаковать содержимое для навигации, WPF предоставляет <xref:System.Windows.Controls.Page> класс. Можно осуществлять переход от одного <xref:System.Windows.Controls.Page> к другому декларативно, с помощью <xref:System.Windows.Documents.Hyperlink> или программно с помощью <xref:System.Windows.Navigation.NavigationService> . WPF использует журнал для запоминания страниц, которые были перемещены из, и для перехода к ним.

<xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.Hyperlink> , <xref:System.Windows.Navigation.NavigationService> , и журнал образуют основу поддержки навигации, предоставляемой WPF. В этом обзоре подробно рассматриваются эти функции, прежде чем будет рассмотрена поддержка расширенной навигации, включающая навигацию по свободным [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файлам, ФАЙЛАМ HTML и объектам.

> [!NOTE]
> В этом разделе термин «браузер» относится только к браузерам, в которых могут размещаться приложения WPF, которые в настоящее время включают в себя Microsoft Internet Explorer и Firefox. Если конкретные функции WPF поддерживаются только определенным браузером, то ссылка на версию обозревателя называется.

## <a name="navigation-in-wpf-applications"></a>Переходы в приложениях WPF

В этом разделе представлен обзор основных возможностей навигации в WPF. Эти возможности доступны как для автономных приложений, так и для XBAP, хотя в этом разделе они представлены в контексте XBAP.

> [!NOTE]
> В этом разделе не рассматривается создание и развертывание XBAP. Дополнительные сведения о XBAP см. в разделе [Общие сведения о приложениях браузера WPF XAML](wpf-xaml-browser-applications-overview.md).

В этом разделе объясняются и демонстрируются следующие аспекты переходов.

- [Реализация страницы](#CreatingAXAMLPage)

- [Настройка начальной страницы](#Configuring_a_Start_Page)

- [Настройка заголовка, ширины и высоты основного окна](#ConfiguringAXAMLPage)

- [Переход по гиперссылке](#NavigatingBetweenXAMLPages)

- [Переход к фрагменту](#FragmentNavigation)

- [Служба переходов](#NavigationService)

- [Программный переход с помощью службы переходов](#Programmatic_Navigation_with_the_Navigation_Service)

- [Время существования перехода](#Navigation_Lifetime)

- [Запоминание перехода в журнале](#NavigationHistory)

- [Время существования страницы и журнал](#PageLifetime)

- [Сохранение состояния содержимого с помощью журнала переходов](#RetainingContentStateWithNavigationHistory)

- [Файлы "cookie"](#Cookies)

- [Структурная навигация](#Structured_Navigation)

<a name="CreatingAXAMLPage"></a>

### <a name="implementing-a-page"></a>Реализация страницы

В WPF можно переходить к нескольким типам содержимого, которые включают .NET Framework объекты, пользовательские объекты, значения перечисления, пользовательские элементы управления, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файлы и HTML-файлы. Однако вы обнаружите, что наиболее распространенным и удобным способом упаковки содержимого является использование <xref:System.Windows.Controls.Page> . Кроме того, <xref:System.Windows.Controls.Page> реализует функции, связанные с навигацией, для улучшения их внешнего вида и упрощения разработки.

С помощью <xref:System.Windows.Controls.Page> можно декларативно реализовать страницу навигации с [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] содержимым с помощью разметки, как в следующем примере.

[!code-xaml[NavigationOverviewSnippets#Page1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]

Объект <xref:System.Windows.Controls.Page> , реализованный в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметке, имеет `Page` как корневой элемент и требует объявления пространства имен XML WPF. `Page`Элемент содержит содержимое, к которому необходимо перейти и отобразить. Содержимое добавляется путем установки `Page.Content` элемента свойства, как показано в следующей разметке.

[!code-xaml[NavigationOverviewSnippets#Page2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]

`Page.Content` может содержать только один дочерний элемент; как предложено в предыдущем примере, содержимым является отдельная строка "Hello, Page!". На практике элемент управления макета обычно используется как дочерний элемент (см. [Макет](../advanced/layout.md)) для хранения и составления содержимого.

Дочерние элементы `Page` элемента считаются содержимым <xref:System.Windows.Controls.Page> и, следовательно, не нужно использовать явное `Page.Content` объявление. Следующая разметка является декларативным эквивалентом предыдущего примера.

[!code-xaml[NavigationOverviewSnippets#Page3XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]

В этом случае `Page.Content` автоматически задается дочерними элементами `Page` элемента. Дополнительные сведения см. в разделе [Модель содержимого WPF](../controls/wpf-content-model.md).

Только разметка <xref:System.Windows.Controls.Page> полезна для отображения содержимого. Однако <xref:System.Windows.Controls.Page> может также отображать элементы управления, позволяющие пользователям взаимодействовать со страницей, и может реагировать на взаимодействие с пользователем, обрабатывая события и вызывая логику приложения. Интерактивный объект <xref:System.Windows.Controls.Page> реализуется с помощью сочетания разметки и кода программной части, как показано в следующем примере.

[!code-xaml[XBAPAppDefSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]

[!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
[!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]

Чтобы разрешить совместную работу файла разметки и файла кода программной части, требуется следующая конфигурация.

- В разметке `Page` элемент должен включать `x:Class` атрибут. При сборке приложения существование `x:Class` в файле разметки заставляет Microsoft Build Engine (MSBuild) создать `partial` класс, производный от, <xref:System.Windows.Controls.Page> и имеет имя, заданное `x:Class` атрибутом. Для этого требуется добавить объявление пространства имен XML для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] схемы ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ). Созданный `partial` класс реализует метод `InitializeComponent` , который вызывается для регистрации событий и задания свойств, реализованных в разметке.

- В коде программной части класс должен быть `partial` классом с тем же именем, который указан `x:Class` атрибутом в разметке и должен быть производным от класса <xref:System.Windows.Controls.Page> . Это позволяет связать файл кода программной части с `partial` классом, созданным для файла разметки при сборке приложения (см. раздел [Создание приложения WPF](building-a-wpf-application-wpf.md)).

- В коде программной части <xref:System.Windows.Controls.Page> класс должен реализовывать конструктор, который вызывает `InitializeComponent` метод. `InitializeComponent`реализуется созданным классом файла разметки `partial` для регистрации событий и задания свойств, определенных в разметке.

> [!NOTE]
> При добавлении нового <xref:System.Windows.Controls.Page> в проект с помощью Visual Studio объект <xref:System.Windows.Controls.Page> реализуется с помощью разметки и кода программной части и включает необходимую конфигурацию для создания связи между файлами разметки и файлов кода программной части, как описано здесь.

После получения можно <xref:System.Windows.Controls.Page> переходить к нему. Чтобы указать первый <xref:System.Windows.Controls.Page> , к которому приложение переходит, необходимо настроить запуск <xref:System.Windows.Controls.Page> .

<a name="Configuring_a_Start_Page"></a>

### <a name="configuring-a-start-page"></a>Настройка начальной страницы

Для XBAP требуется определенное количество инфраструктуры приложений, размещаемых в браузере. В WPF <xref:System.Windows.Application> класс является частью определения приложения, которое устанавливает необходимую инфраструктуру приложений (см. [Обзор управления приложениями](application-management-overview.md)).

Определение приложения обычно реализуется с помощью разметки и кода программной части с файлом разметки, настроенным в качестве `ApplicationDefinition` элемента MSBuild. Ниже приведено определение приложения для XBAP.

[!code-xaml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

[!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
[!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]

XBAP может использовать определение приложения для указания запуска <xref:System.Windows.Controls.Page> , который <xref:System.Windows.Controls.Page> автоматически загружается при запуске XBAP. Это можно сделать, задав <xref:System.Windows.Application.StartupUri%2A> свойству универсальный код ресурса (URI) для требуемого значения <xref:System.Windows.Controls.Page> .

> [!NOTE]
> В большинстве случаев объект <xref:System.Windows.Controls.Page> либо компилируется в приложение, либо развертывается вместе с ним. В этих случаях URI, определяющий, <xref:System.Windows.Controls.Page> — это URI типа "Pack", который соответствует схеме *Pack* . URI типа "Pack" обсуждаются далее в URI типа " [Pack" в WPF](pack-uris-in-wpf.md). Для перехода к содержимому можно также использовать схему HTTP, которая рассматривается далее.

Можно задать <xref:System.Windows.Application.StartupUri%2A> декларативно в разметке, как показано в следующем примере.

[!code-xaml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

В этом примере `StartupUri` атрибут задается с помощью относительного URI типа Pack, определяющего Homepage. XAML. При запуске XBAP автоматически осуществляется переход на страницу HomePage. XAML и ее отображение. Это продемонстрировано на следующем рисунке, в котором показан XBAP, запущенный с веб-сервера.

![XBAP-страница](./media/navigation-overview/xbap-launched-from-a-web-server.png "Это показывает, что XBAP запускается с веб-сервера.")

> [!NOTE]
> Дополнительные сведения о разработке и развертывании XBAP см. в разделе [Общие сведения о приложениях браузера WPF XAML](wpf-xaml-browser-applications-overview.md) и [развертывании приложения WPF](deploying-a-wpf-application-wpf.md).

<a name="ConfiguringAXAMLPage"></a>

### <a name="configuring-the-host-windows-title-width-and-height"></a>Настройка заголовка, ширины и высоты основного окна

Первое, что вы могли заметить на предыдущем рисунке, заключается в том, что заголовок в браузере и на панели вкладок является универсальным кодом ресурса (URI) для XBAP. Заголовок не только длинный, но также не является ни привлекательным, ни информативным. По этой причине <xref:System.Windows.Controls.Page> предлагает способ изменить заголовок, задав <xref:System.Windows.Controls.Page.WindowTitle%2A> свойство. Кроме того, можно настроить ширину и высоту окна браузера, установив <xref:System.Windows.Controls.Page.WindowWidth%2A> и <xref:System.Windows.Controls.Page.WindowHeight%2A> соответственно.

<xref:System.Windows.Controls.Page.WindowTitle%2A>, <xref:System.Windows.Controls.Page.WindowWidth%2A> и <xref:System.Windows.Controls.Page.WindowHeight%2A> могут быть заданы декларативно в разметке, как показано в следующем примере.

[!code-xaml[NavigationOverviewSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]

Результат показан на примере ниже.

![Название окна, высота, ширина](./media/navigation-overview/window-title-width-height.png "Отображается заголовок, высота и ширина окна, которые можно настроить.")

<a name="NavigatingBetweenXAMLPages"></a>

### <a name="hyperlink-navigation"></a>Переход по гиперссылке

Типичный XBAP состоит из нескольких страниц. Самый простой способ перехода с одной страницы на другой — использовать <xref:System.Windows.Documents.Hyperlink> . Можно декларативно добавить <xref:System.Windows.Documents.Hyperlink> в объект, <xref:System.Windows.Controls.Page> используя `Hyperlink` элемент, который показан в следующей разметке.

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

Для `Hyperlink` элемента требуется следующее:

- URI типа Pack для <xref:System.Windows.Controls.Page> перехода в, как указано в `NavigateUri` атрибуте.

- Содержимое, которое пользователь может щелкнуть для инициации навигации, например текст и изображения (для содержимого, которое `Hyperlink` может содержать элемент, см. раздел <xref:System.Windows.Documents.Hyperlink> ).

На следующем рисунке показан XBAP с <xref:System.Windows.Controls.Page> <xref:System.Windows.Documents.Hyperlink> .

![Страница с гиперссылкой](./media/navigation-overview/xbap-with-a-page-with-a-hyperlink.png "Это показывает XBAP со страницей с гиперссылкой.")

Как и следовало бы ожидания, нажатие кнопки <xref:System.Windows.Documents.Hyperlink> вызывает переход XBAP к объекту <xref:System.Windows.Controls.Page> , определяемому `NavigateUri` атрибутом. Кроме того, XBAP добавляет запись для предыдущего <xref:System.Windows.Controls.Page> списка «Последние страницы» в Internet Explorer. Это показано на следующем рисунке.

![Кнопки назад и вперед](./media/navigation-overview/back-and-forward-navigation.png "Переход с помощью кнопок назад и вперед.")

А также поддержка переходов от одного <xref:System.Windows.Controls.Page> к другому, <xref:System.Windows.Documents.Hyperlink> также поддерживает навигацию по фрагментам.

<a name="FragmentNavigation"></a>

### <a name="fragment-navigation"></a>Переход к фрагменту

*Навигация по фрагментам* — это переход к фрагменту содержимого в текущем <xref:System.Windows.Controls.Page> или другом <xref:System.Windows.Controls.Page> . В WPF фрагмент содержимого — это содержимое, содержащееся в именованном элементе. Именованный элемент — это элемент с `Name` установленным атрибутом. В следующей разметке показан именованный `TextBlock` элемент, содержащий фрагмент содержимого.

[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]

Для <xref:System.Windows.Documents.Hyperlink> перехода к фрагменту содержимого `NavigateUri` атрибут должен включать следующее:

- Универсальный код ресурса (URI) <xref:System.Windows.Controls.Page> с фрагментом содержимого, к которому необходимо выполнить переход.

- Символ "#".

- Имя элемента <xref:System.Windows.Controls.Page> , содержащего фрагмент содержимого.

URI фрагмента имеет следующий формат.

*URI_страницы* `#` *имя_элемента*.

Ниже приведен пример `Hyperlink` , который настроен для перехода к фрагменту содержимого.

[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]

> [!NOTE]
> В этом разделе описывается реализация навигации по умолчанию для фрагментов в WPF. WPF также позволяет реализовать собственную схему навигации по фрагментам, которая, в свою часть, требует обработки <xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=nameWithType> события.

> [!IMPORTANT]
> Можно перейти к фрагментам на несвободных [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницах (файлы только разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] с `Page` корневым элементом), только если страницы можно просматривать по протоколу HTTP.
>
> Однако свободная [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страница может переходить к собственным фрагментам.

<a name="NavigationService"></a>

### <a name="navigation-service"></a>Служба переходов

Хотя <xref:System.Windows.Documents.Hyperlink> позволяет пользователю инициировать навигацию по конкретному <xref:System.Windows.Controls.Page> , работа по поиску и скачиванию страницы выполняется <xref:System.Windows.Navigation.NavigationService> классом. По сути, <xref:System.Windows.Navigation.NavigationService> предоставляет возможность обработки запроса навигации от имени клиентского кода, например <xref:System.Windows.Documents.Hyperlink> . Кроме того, <xref:System.Windows.Navigation.NavigationService> реализует поддержку более высокого уровня для отслеживания и влияния на запрос навигации.

При <xref:System.Windows.Documents.Hyperlink> нажатии кнопки WPF вызывает метод, <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> чтобы нахождение и скачивание по <xref:System.Windows.Controls.Page> указанному URI типа pack. Загруженный файл <xref:System.Windows.Controls.Page> преобразуется в дерево объектов, корневой объект которых является экземпляром скачанного <xref:System.Windows.Controls.Page> . Ссылка на корневой <xref:System.Windows.Controls.Page> объект хранится в <xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=nameWithType> свойстве. URI типа "Pack" для содержимого, к которому осуществлялся переход, хранится в <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> свойстве, а в <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=nameWithType> хранится URI типа "Pack" для последней страницы, к которой был выполнен переход.

> [!NOTE]
> Приложение WPF может иметь более одного активного в данный момент <xref:System.Windows.Navigation.NavigationService> . Дополнительные сведения см. в подразделе [узлы навигации](#Navigation_Hosts) далее в этой статье.

<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>

### <a name="programmatic-navigation-with-the-navigation-service"></a>Программный переход с помощью службы переходов

Вам не нужно знать о том <xref:System.Windows.Navigation.NavigationService> , реализована ли Навигация декларативно в разметке с помощью <xref:System.Windows.Documents.Hyperlink> , поскольку <xref:System.Windows.Documents.Hyperlink> использует от <xref:System.Windows.Navigation.NavigationService> вашего имени. Это означает, что, если прямой или непрямой родительский элемент a <xref:System.Windows.Documents.Hyperlink> является узлом навигации (см. раздел [навигационные узлы](#Navigation_Hosts)), сможет <xref:System.Windows.Documents.Hyperlink> найти и использовать службу навигации узла навигации для обработки запроса навигации.

Однако существуют ситуации, когда необходимо использовать <xref:System.Windows.Navigation.NavigationService> напрямую, включая следующие.

- Если необходимо создать экземпляр <xref:System.Windows.Controls.Page> с использованием конструктора без параметров.

- Если необходимо задать свойства для, <xref:System.Windows.Controls.Page> прежде чем переходить к нему.

- Если нужно выполнить <xref:System.Windows.Controls.Page> Переход к, можно определить только во время выполнения.

В таких ситуациях необходимо написать код для программной инициации навигации путем вызова <xref:System.Windows.Navigation.NavigationService.Navigate%2A> метода <xref:System.Windows.Navigation.NavigationService> объекта. Для этого требуется получить ссылку на <xref:System.Windows.Navigation.NavigationService> .

#### <a name="getting-a-reference-to-the-navigationservice"></a>Получение ссылки на службу переходов

По причинам, описанным в разделе [узлы навигации](#Navigation_Hosts) , приложение WPF может иметь более одного <xref:System.Windows.Navigation.NavigationService> . Это означает, что вашему коду нужен способ поиска <xref:System.Windows.Navigation.NavigationService> , который обычно используется <xref:System.Windows.Navigation.NavigationService> для перехода к текущему <xref:System.Windows.Controls.Page> . Чтобы получить ссылку на, можно <xref:System.Windows.Navigation.NavigationService> вызвать `static` <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A?displayProperty=nameWithType> метод. Чтобы получить объект <xref:System.Windows.Navigation.NavigationService> , который переходит к определенному объекту <xref:System.Windows.Controls.Page> , в <xref:System.Windows.Controls.Page> качестве аргумента метода передается ссылка <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A> . В следующем коде показано, как получить <xref:System.Windows.Navigation.NavigationService> для текущего <xref:System.Windows.Controls.Page> .

[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]

В качестве ярлыка для поиска <xref:System.Windows.Navigation.NavigationService> для <xref:System.Windows.Controls.Page> , <xref:System.Windows.Controls.Page> реализует <xref:System.Windows.Controls.Page.NavigationService%2A> свойство. Эти действия показаны в следующем примере.

[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]

> [!NOTE]
> <xref:System.Windows.Controls.Page> <xref:System.Windows.Navigation.NavigationService> При <xref:System.Windows.Controls.Page> вызове события может получиться только ссылка на него <xref:System.Windows.FrameworkElement.Loaded> .

#### <a name="programmatic-navigation-to-a-page-object"></a>Программный переход к объекту страницы

В следующем примере показано, как использовать <xref:System.Windows.Navigation.NavigationService> для программного перехода к <xref:System.Windows.Controls.Page> . Программная Навигация необходима, так как <xref:System.Windows.Controls.Page> для перехода к которому можно создать экземпляр только с помощью одного конструктора без параметров. Объект <xref:System.Windows.Controls.Page> с конструктором без параметров показан в следующей разметке и коде.

[!code-xaml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]

[!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
[!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]

Объект <xref:System.Windows.Controls.Page> , который переходит к элементу <xref:System.Windows.Controls.Page> с конструктором без параметров, показан в следующей разметке и коде.

[!code-xaml[NavigationOverviewSnippets#NSNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]

При <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.Controls.Page> нажатии кнопки переход инициируется путем создания экземпляра <xref:System.Windows.Controls.Page> компонента для перехода к использованию конструктора без параметров и вызова <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> метода. <xref:System.Windows.Navigation.NavigationService.Navigate%2A>принимает ссылку на объект, <xref:System.Windows.Navigation.NavigationService> к которому будет переходить, а не к URI типа pack.

#### <a name="programmatic-navigation-with-a-pack-uri"></a>Программный переход с URI типа pack

Если необходимо создать URI типа "Pack" программным способом (например, при определении URI типа "Pack" во время выполнения), можно использовать <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> метод. Эти действия показаны в следующем примере.

[!code-xaml[NavigationOverviewSnippets#NSUriNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]

#### <a name="refreshing-the-current-page"></a>Обновление текущей страницы

Объект <xref:System.Windows.Controls.Page> не загружается, если он имеет тот же URI типа Pack, что и URI типа Pack, хранящийся в <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> свойстве. Чтобы принудительно загрузить текущую страницу в WPF, можно вызвать <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType> метод, как показано в следующем примере.

[!code-xaml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]

[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]

<a name="Navigation_Lifetime"></a>

### <a name="navigation-lifetime"></a>Время существования перехода

Как вы уже видели, существует множество способов инициации перехода. При инициации навигации и при выполнении навигации можно отслеживать и повлиять на навигацию с помощью следующих событий, реализуемых <xref:System.Windows.Navigation.NavigationService> :

- <xref:System.Windows.Navigation.NavigationService.Navigating>. Появляется, когда запрошен новый переход. Можно использовать для отмены перехода.

- <xref:System.Windows.Navigation.NavigationService.NavigationProgress>. Происходит периодически во время загрузки, тем самым предоставляя информацию о ходе процесса навигации.

- <xref:System.Windows.Navigation.NavigationService.Navigated>. Появляется, когда страница найдена и загружена.

- <xref:System.Windows.Navigation.NavigationService.NavigationStopped>. Происходит при остановке навигации (путем вызова <xref:System.Windows.Navigation.NavigationService.StopLoading%2A> ) или при запросе новой навигации во время выполнения текущей навигации.

- <xref:System.Windows.Navigation.NavigationService.NavigationFailed>. Появляется при возникновении ошибки во время перехода к запрошенному содержимому.

- <xref:System.Windows.Navigation.NavigationService.LoadCompleted>. Появляется, когда содержимое, к которому был осуществлен переход, загружено и проанализировано и начинается его отрисовка.

- <xref:System.Windows.Navigation.NavigationService.FragmentNavigation>. Появляется в начале перехода к фрагменту содержимого, который происходит:

  - немедленно, если нужный фрагмент находится в текущем содержимом;

  - после загрузки исходного содержимого, если нужный фрагмент находится в другом содержимом.

События перехода вызываются в порядке, который показан на следующем рисунке.

![Таблица потока навигации страницы](./media/navigation-overview/order-of-navigation-events.png "Блок-схема событий навигации по страницам")

Как правило, это <xref:System.Windows.Controls.Page> не касается этих событий. Более вероятно, что приложение связано с ними, и по этой причине эти события также вызываются <xref:System.Windows.Application> классом:

- <xref:System.Windows.Application.Navigating?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationProgress?displayProperty=nameWithType>

- <xref:System.Windows.Application.Navigated?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationFailed?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationStopped?displayProperty=nameWithType>

- <xref:System.Windows.Application.LoadCompleted?displayProperty=nameWithType>

- <xref:System.Windows.Application.FragmentNavigation?displayProperty=nameWithType>

Каждый раз при <xref:System.Windows.Navigation.NavigationService> вызове события <xref:System.Windows.Application> класс вызывает соответствующее событие. <xref:System.Windows.Controls.Frame>и <xref:System.Windows.Navigation.NavigationWindow> предлагают те же события для обнаружения переходов в соответствующих областях.

В некоторых случаях <xref:System.Windows.Controls.Page> может заинтересовать эти события. Например, <xref:System.Windows.Controls.Page> может обработано <xref:System.Windows.Navigation.NavigationService.Navigating?displayProperty=nameWithType> событие, чтобы определить, следует ли отменить переход от самого себя. Эти действия показаны в следующем примере.

[!code-xaml[NavigationOverviewSnippets#CancelNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]

При регистрации обработчика с событием навигации из <xref:System.Windows.Controls.Page> , как в предыдущем примере, необходимо также отменить регистрацию обработчика событий. В противном случае могут возникнуть побочные эффекты в отношении того, как Навигация WPF запоминает <xref:System.Windows.Controls.Page> навигацию с помощью журнала.

<a name="NavigationHistory"></a>

### <a name="remembering-navigation-with-the-journal"></a>Запоминание перехода в журнале

WPF использует два стека для запоминания страниц, из которых вы перешли: стек назад и прямой стек. При переходе от текущего объекта <xref:System.Windows.Controls.Page> к новому <xref:System.Windows.Controls.Page> или пересылке к существующему объекту <xref:System.Windows.Controls.Page> , текущий <xref:System.Windows.Controls.Page> добавляется в *стек назад*. При переходе от текущего момента <xref:System.Windows.Controls.Page> к предыдущему <xref:System.Windows.Controls.Page> , текущее значение <xref:System.Windows.Controls.Page> добавляется в *стек вперед*. Стек "Назад", стек "Вперед" и функциональные возможности для управления ими в совокупности называются журналом. Каждый элемент в стеке заднего и прямого стека является экземпляром <xref:System.Windows.Navigation.JournalEntry> класса и называется *записью в журнале*.

#### <a name="navigating-the-journal-from-internet-explorer"></a>Перемещение по журналу в браузере Internet Explorer

По сути, журнал работает так же, как кнопки **назад** и **вперед** в Internet Explorer. Это показано на следующем рисунке.

![Кнопки назад и вперед](./media/navigation-overview/back-and-forward-navigation.png "Переход с помощью кнопок назад и вперед.")

Для XBAP, размещенных в Internet Explorer, WPF интегрирует журнал в навигацию по [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Internet Explorer. Это позволяет пользователям перемещаться по страницам в XBAP с помощью кнопок **назад**, **вперед**и **Последние страницы** в Internet Explorer.

> [!IMPORTANT]
> В Internet Explorer, когда пользователь отключается от XBAP и возвращается к нему, только записи журнала для страниц, которые не были сохранены в активном состоянии, сохраняются в журнале. Сведения о сохранении страниц в активном состоянии см. в разделе [время существования страницы и журнал](#PageLifetime) далее в этой статье.

По умолчанию текст <xref:System.Windows.Controls.Page> , отображаемый в списке **Последние страницы** Internet Explorer, является универсальным кодом ресурса (URI) для <xref:System.Windows.Controls.Page> . В большинстве случаев это не особенно важно для пользователя. К счастью можно изменить текст, используя следующие параметры.

1. Значение присоединенного `JournalEntry.Name` атрибута.

2. `Page.Title`Значение атрибута.

3. `Page.WindowTitle`Значение атрибута и универсальный код ресурса (URI) для текущего <xref:System.Windows.Controls.Page> .

4. Универсальный код ресурса (URI) для текущего <xref:System.Windows.Controls.Page> . (по умолчанию)

Порядок, в котором перечислены параметры, совпадает с порядком приоритета для поиска текста. Например, если `JournalEntry.Name` задано значение, другие значения игнорируются.

В следующем примере атрибут используется `Page.Title` для изменения текста, отображаемого для записи журнала.

[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]

[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]

#### <a name="navigating-the-journal-using-wpf"></a>Перемещение по журналу с помощью WPF

Хотя пользователь может перемещаться по журналу с помощью страниц « **назад**», « **вперед**» и « **последние** » в Internet Explorer, можно также перемещаться по журналу с помощью декларативных и программных механизмов, предоставляемых WPF. Одной из причин для этого является предоставление пользовательских интерфейсов навигации на страницах.

Можно декларативно добавить поддержку навигации по журналам с помощью команд навигации, предоставляемых <xref:System.Windows.Input.NavigationCommands> . В следующем примере показано, как использовать `BrowseBack` команду навигации.

[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]

Можно программно перемещаться по журналу с помощью одного из следующих членов <xref:System.Windows.Navigation.NavigationService> класса:

- <xref:System.Windows.Navigation.NavigationService.GoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.GoForward%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>

Журнал также можно манипулировать программно, как описано в статье [Сохранение состояния содержимого с помощью журнала переходов](#RetainingContentStateWithNavigationHistory) далее в этом разделе.

<a name="PageLifetime"></a>

### <a name="page-lifetime-and-the-journal"></a>Время существования страницы и журнал

Рассмотрим XBAP с несколькими страницами, содержащими обширное содержимое, включая графику, анимацию и мультимедиа. Объем памяти для подобных страниц может быть довольно большим, особенно если используются видеоматериалы и звуковые файлы. Учитывая, что журнал "запоминает" страницы, к которым был выполнен переход, может быстро использовать большой и заметный объем памяти.

По этой причине поведение журнала по умолчанию заключается в хранении <xref:System.Windows.Controls.Page> метаданных в каждой записи журнала, а не в ссылке на <xref:System.Windows.Controls.Page> объект. При переходе к записи журнала ее <xref:System.Windows.Controls.Page> метаданные используются для создания нового экземпляра указанного объекта <xref:System.Windows.Controls.Page> . Как следствие, каждый <xref:System.Windows.Controls.Page> , к которому осуществляется переход, имеет время существования, показанное на следующем рисунке.

![Время существования страницы](./media/navigation-overview/navigated-page-lifetime.png "Это показывает время существования перехода на страницу.")

Несмотря на то, что использование поведения ведения журнала по умолчанию может сэкономить на потреблении памяти, производительность отрисовки на странице может снизиться; <xref:System.Windows.Controls.Page>при повторном создании экземпляра может потребоваться много времени, особенно если у него много содержимого. Если необходимо хранить <xref:System.Windows.Controls.Page> экземпляр в журнале, можно нарисовать два метода для этого. Во-первых, можно программным путем выполнить переход к <xref:System.Windows.Controls.Page> объекту, вызвав <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> метод.

Во-вторых, можно указать, что WPF будет хранить экземпляр <xref:System.Windows.Controls.Page> в журнале, задав <xref:System.Windows.Controls.Page.KeepAlive%2A> для свойства значение `true` (значение по умолчанию — `false` ). Как показано в следующем примере, можно задать <xref:System.Windows.Controls.Page.KeepAlive%2A> декларативно в разметке.

[!code-xaml[NavigationOverviewSnippets#KeepAlivePageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]

Время существования объекта <xref:System.Windows.Controls.Page> , который хранится в активном состоянии, незначительно отличается от того, который не является. <xref:System.Windows.Controls.Page>При первом переходе к объекту, который хранится в активном состоянии, он создается так же, как и объект <xref:System.Windows.Controls.Page> , который не поддерживается в активном состоянии. Однако, поскольку экземпляр класса <xref:System.Windows.Controls.Page> хранится в журнале, он никогда не создается повторно в течение времени, пока он остается в журнале. Следовательно, если <xref:System.Windows.Controls.Page> имеется логика инициализации, которая должна вызываться при каждом <xref:System.Windows.Controls.Page> переходе к, необходимо переместить его из конструктора в обработчик <xref:System.Windows.FrameworkElement.Loaded> события. Как показано на следующем рисунке, <xref:System.Windows.FrameworkElement.Loaded> <xref:System.Windows.FrameworkElement.Unloaded> события и по-прежнему создаются каждый раз, когда <xref:System.Windows.Controls.Page> осуществляется переход к и из соответственно.

![При генерации событий загрузки и выгрузки](./media/navigation-overview/loaded-and-unloaded-events.png "Загруженные и выгруженные события вызываются при переходе на страницу и из нее.")

Если <xref:System.Windows.Controls.Page> не поддерживается в активном состоянии, не следует выполнять одно из следующих действий.

- Сохранять ссылку или любую его часть.

- Регистрировать обработчики событий с событиями, которые не реализованы в объекте.

При выполнении любого из этих действий будут созданы ссылки, которые принудительно <xref:System.Windows.Controls.Page> будут сохранены в памяти даже после удаления из журнала.

Как правило, предпочтительнее использовать поведение по умолчанию, <xref:System.Windows.Controls.Page> не сохраняя <xref:System.Windows.Controls.Page> активность. Однако при этом существуют реализации состояния, которые описаны в следующем разделе.

<a name="RetainingContentStateWithNavigationHistory"></a>

### <a name="retaining-content-state-with-navigation-history"></a>Сохранение состояния содержимого с помощью журнала переходов

Если объект <xref:System.Windows.Controls.Page> не хранится в активном состоянии и содержит элементы управления, собирающие данные от пользователя, что произойдет с данными, если пользователь отрывается от и обратно <xref:System.Windows.Controls.Page> ? С точки зрения пользователя следует ожидать появления ранее введенных данных. К сожалению, поскольку новый экземпляр класса <xref:System.Windows.Controls.Page> создается с каждой навигацией, элементы управления, которые собирают данные, повторно создают экземпляры, а данные теряются.

К счастью, журнал обеспечивает поддержку для запоминания данных во всех <xref:System.Windows.Controls.Page> переходах, включая управляющие данные. В частности, запись журнала для каждого <xref:System.Windows.Controls.Page> из них выступает в качестве временного контейнера для связанного <xref:System.Windows.Controls.Page> состояния. Следующие шаги показывают, как эта поддержка используется при <xref:System.Windows.Controls.Page> переходе от:

1. Запись для текущего объекта <xref:System.Windows.Controls.Page> добавляется в журнал.

2. Состояние объекта хранится в <xref:System.Windows.Controls.Page> записи журнала для этой страницы, которая добавляется в стек назад.

3. Новый <xref:System.Windows.Controls.Page> Переход к.

При <xref:System.Windows.Controls.Page> переходе назад к странице с помощью журнала выполняются следующие действия.

1. Создается <xref:System.Windows.Controls.Page> экземпляр (верхняя запись журнала в стеке сзади).

2. <xref:System.Windows.Controls.Page>Обновляет состояние, которое было сохранено с записью журнала для <xref:System.Windows.Controls.Page> .

3. <xref:System.Windows.Controls.Page>Переходит обратно к.

WPF автоматически использует эту поддержку при использовании следующих элементов управления в <xref:System.Windows.Controls.Page> :

- <xref:System.Windows.Controls.CheckBox>

- <xref:System.Windows.Controls.ComboBox>

- <xref:System.Windows.Controls.Expander>

- <xref:System.Windows.Controls.Frame>

- <xref:System.Windows.Controls.ListBox>

- <xref:System.Windows.Controls.ListBoxItem>

- <xref:System.Windows.Controls.MenuItem>

- <xref:System.Windows.Controls.ProgressBar>

- <xref:System.Windows.Controls.RadioButton>

- <xref:System.Windows.Controls.Slider>

- <xref:System.Windows.Controls.TabControl>

- <xref:System.Windows.Controls.TabItem>

- <xref:System.Windows.Controls.TextBox>

Если <xref:System.Windows.Controls.Page> компонент использует эти элементы управления, данные, которые они записывают в них, запоминаются по <xref:System.Windows.Controls.Page> переходам, как показано **на** <xref:System.Windows.Controls.ListBox> следующем рисунке.

![Страница с элементами управления, помнящими состояние](./media/navigation-overview/data-remembered-across-page-navigations.png "Указанные данные запоминаются по переходам между страницами.")

Если <xref:System.Windows.Controls.Page> у элемента есть элементы управления, отличные от указанных в приведенном выше списке, или если состояние хранится в пользовательских объектах, необходимо написать код, чтобы журнал запомнил состояние в ходе <xref:System.Windows.Controls.Page> переходов.

Если необходимо запомнить небольшие элементы состояния при <xref:System.Windows.Controls.Page> переходах, можно использовать свойства зависимостей (см <xref:System.Windows.DependencyProperty> .), настроенные с <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType> флагом метаданных.

Если ваше состояние, которое необходимо <xref:System.Windows.Controls.Page> Запомнить в переходах, состоит из нескольких фрагментов данных, может оказаться, что для инкапсуляции вашего состояния в один класс и реализации интерфейса будет использоваться меньше кода <xref:System.Windows.Navigation.IProvideCustomContentState> .

Если необходимо перемещаться по различным состояниям одного объекта <xref:System.Windows.Controls.Page> , не переходя от <xref:System.Windows.Controls.Page> самого себя, можно использовать <xref:System.Windows.Navigation.IProvideCustomContentState> и <xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=nameWithType> .

<a name="Cookies"></a>

### <a name="cookies"></a>Файлы cookie

Другой способ, которым приложения WPF могут хранить данные, — это файлы cookie, которые создаются, обновляются и удаляются с помощью <xref:System.Windows.Application.SetCookie%2A> <xref:System.Windows.Application.GetCookie%2A> методов и. Файлы cookie, которые можно создать в WPF, — это те же файлы cookie, которые используются другими типами веб-приложений. файлы cookie — это произвольные фрагменты данных, которые хранятся приложением на клиентском компьютере во время или между сеансами приложения. Данные файлов cookie обычно представлены в форме пары "имя — значение" в следующем формате.

*Имя* `=` *Значение*

При передаче данных <xref:System.Windows.Application.SetCookie%2A> вместе с <xref:System.Uri> расположением, для которого должен быть задан файл cookie, файл cookie создается в памяти и доступен только в течение текущего сеанса приложения. Этот тип файлов cookie называется *сеансом cookie*.

Чтобы сохранить файл cookie на протяжении нескольких сеансов приложения, необходимо добавить в файл cookie дату окончания срока действия, используя следующий формат.

*имя* `=` *значение* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`

Файл cookie с датой окончания срока действия хранится в папке временных файлов временной папки установки Windows до истечения срока действия файла cookie. Такой файл cookie называется *постоянным файлом cookie* , так как он сохраняется во всех сеансах приложения.

Вы получаете как сеанс, так и постоянные файлы cookie, вызывая <xref:System.Windows.Application.GetCookie%2A> метод, передав <xref:System.Uri> расположение, где файл cookie был задан <xref:System.Windows.Application.SetCookie%2A> методом.

Ниже приведены некоторые способы поддержки файлов cookie в WPF.

- Автономные приложения WPF и XBAP могут создавать файлы cookie и управлять ими.

- Файлы cookie, созданные XBAP, можно получить из браузера.

- XBAP из одного домена могут создавать файлы cookie и совместно использовать их.

- XBAP и HTML-страницы из одного домена могут создавать файлы cookie и совместно использовать их.

- Файлы cookie отправляются, когда XBAP и свободные [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницы выполняют веб-запросы.

- ПРИЛОЖЕНИЯ и приложения XBAP верхнего уровня, размещенные в IFRAME, имеют доступ к файлам cookie.

- Поддержка файлов cookie в WPF одинакова для всех поддерживаемых браузеров.

- В Internet Explorer политика P3P, относящаяся к файлам cookie, учитывается WPF, особенно в отношении сторонних разработчиков и XBAP.

<a name="Structured_Navigation"></a>

### <a name="structured-navigation"></a>Структурная навигация

Если необходимо передать данные из одного <xref:System.Windows.Controls.Page> в другой, можно передать данные в качестве аргументов в конструктор без параметров <xref:System.Windows.Controls.Page> . Обратите внимание, что при использовании этого метода необходимо поддерживать активность. в противном случае при <xref:System.Windows.Controls.Page> следующем переходе к <xref:System.Windows.Controls.Page> WPF повторно создает экземпляр с <xref:System.Windows.Controls.Page> помощью конструктора без параметров.

Кроме того, <xref:System.Windows.Controls.Page> можно реализовать свойства, которые устанавливаются с данными, которые необходимо передать. Однако, когда нужно <xref:System.Windows.Controls.Page> передать данные обратно в объект <xref:System.Windows.Controls.Page> , к которому осуществляется переход. Проблема заключается в том, что Навигация изначально не поддерживает механизмы, гарантирующие, что <xref:System.Windows.Controls.Page> будет возвращено значение после перехода от. По существу переходы не поддерживают семантику вызова/возврата. Для решения этой проблемы WPF предоставляет <xref:System.Windows.Navigation.PageFunction%601> класс, который можно использовать, чтобы гарантировать, что компонент <xref:System.Windows.Controls.Page> возвращается в прогнозируемом и структурированном виде. Дополнительные сведения см. в разделе [Общие сведения о структурной навигации](structured-navigation-overview.md).

<a name="The_NavigationWindow_Class"></a>

## <a name="the-navigationwindow-class"></a>Класс NavigationWindow

К этому моменту мы рассмотрели целый ряд служб переходов, которые с наибольшей вероятностью будут использоваться для построения приложений с содержимым, допускающим переходы. Эти службы обсуждались в контексте XBAP, хотя они не ограничиваются XBAP. Современные операционные системы и приложения для Windows используют преимущества браузера современных пользователей, чтобы внедрить навигацию в стиле браузера в автономные приложения. Ниже приведены распространенные примеры.

- **Тезаурус**: переход по вариантам слов.

- **Обозреватель файлов**: переход по файлам и папкам.

- **Мастеры**: разбиение сложной задачи на несколько страниц, по которым можно перемещаться. Примером является мастер компонентов Windows, который обрабатывает Добавление и удаление компонентов Windows.

Чтобы включить навигацию в стиле браузера в автономные приложения, можно использовать <xref:System.Windows.Navigation.NavigationWindow> класс. <xref:System.Windows.Navigation.NavigationWindow>является производным от <xref:System.Windows.Window> и расширяет его с помощью одной и той же поддержки навигации, предоставляемой XBAP. Можно использовать <xref:System.Windows.Navigation.NavigationWindow> в качестве главного окна автономного приложения или вторичного окна, такого как диалоговое окно.

Для реализации <xref:System.Windows.Navigation.NavigationWindow> , как и в большинстве классов верхнего уровня в WPF ( <xref:System.Windows.Window> , <xref:System.Windows.Controls.Page> и т. д.), используется сочетание разметки и кода программной части. Эти действия показаны в следующем примере.

[!code-xaml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]

[!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
[!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]

Этот код создает объект <xref:System.Windows.Navigation.NavigationWindow> , который автоматически переходит на <xref:System.Windows.Controls.Page> страницу (Homepage. XAML) при <xref:System.Windows.Navigation.NavigationWindow> открытии. Если <xref:System.Windows.Navigation.NavigationWindow> является основным окном приложения, можно использовать `StartupUri` атрибут для его запуска. Это показано в следующем примере разметки.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]

На следующем рисунке показано в <xref:System.Windows.Navigation.NavigationWindow> качестве главного окна автономного приложения.

![Главное окно](./media/navigation-overview/navigation-window-as-main-window.png "Окно навигации как главное окно")

На рисунке видно, что <xref:System.Windows.Navigation.NavigationWindow> имеет заголовок, даже если он не был задан в <xref:System.Windows.Navigation.NavigationWindow> коде реализации из предыдущего примера. Вместо этого заголовок задается с помощью <xref:System.Windows.Controls.Page.WindowTitle%2A> свойства, которое показано в следующем коде.

[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]
[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]

Установка <xref:System.Windows.Controls.Page.WindowWidth%2A> свойств и <xref:System.Windows.Controls.Page.WindowHeight%2A> также влияет на <xref:System.Windows.Navigation.NavigationWindow> .

Обычно вы реализуете свой собственный, <xref:System.Windows.Navigation.NavigationWindow> когда необходимо настроить его поведение или внешний вид. Если вы этого не сделали, можно использовать команду быстрого вызова. Если указать URI типа "Pack" в <xref:System.Windows.Controls.Page> как <xref:System.Windows.Application.StartupUri%2A> в автономном приложении, <xref:System.Windows.Application> автоматически создает <xref:System.Windows.Navigation.NavigationWindow> для размещения <xref:System.Windows.Controls.Page> . В следующем примере разметки показано, как это сделать.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchPage](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]

Если требуется, чтобы дополнительное окно приложения, такое как диалоговое окно, было <xref:System.Windows.Navigation.NavigationWindow> , можно использовать код, приведенный в следующем примере, чтобы открыть его.

[!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
[!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]

На рисунке ниже показан результат.

![Диалоговое окно](./media/navigation-overview/navigation-window-as-dialog-box.png "Окно навигации как диалоговое окно")

Как видите, <xref:System.Windows.Navigation.NavigationWindow> отображаются кнопки **назад** и **вперед** в стиле Internet Explorer, позволяющие пользователям перемещаться по журналу. Эти кнопки предоставляют пользователям те же возможности, что показаны на следующем рисунке.

![Кнопки “Дальше” и “Назад” в NavigationWindow](./media/navigation-overview/back-and-forward-buttons-in-navigation-window.png "Кнопки назад и вперед в окне навигации")

Если страницы предоставляют собственную поддержку навигации по журналам и пользовательский интерфейс, можно скрыть кнопки **назад** и **вперед** , выводимые <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> свойством, задав для свойства значение `false` .

Кроме того, можно использовать поддержку настройки в WPF, чтобы заменить [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] <xref:System.Windows.Navigation.NavigationWindow> саму себя.

<a name="Frame_in_Standalone_Applications"></a>

## <a name="the-frame-class"></a>Класс Frame

Как браузер, так и <xref:System.Windows.Navigation.NavigationWindow> окна, в которых размещается содержимое для навигации. В некоторых случаях приложения имеют содержимое, которое не обязательно должно размещаться в целом окне. Такое содержимое помещается внутрь другого содержимого. Можно вставить содержимое для навигации в другое содержимое с помощью <xref:System.Windows.Controls.Frame> класса. <xref:System.Windows.Controls.Frame>предоставляет такую же поддержку, как <xref:System.Windows.Navigation.NavigationWindow> и XBAP.

В следующем примере показано, как добавить <xref:System.Windows.Controls.Frame> к <xref:System.Windows.Controls.Page> декларативно с помощью `Frame` элемента.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]

Эта разметка задает `Source` атрибут `Frame` элемента с URI типа Pack для, <xref:System.Windows.Controls.Page> который <xref:System.Windows.Controls.Frame> должен изначально переходить к. На следующем рисунке показан XBAP с объект, <xref:System.Windows.Controls.Page> имеющий <xref:System.Windows.Controls.Frame> Переход между несколькими страницами.

![Фрейм, осуществивший переход по нескольким страницам](./media/navigation-overview/frame-navigation-between-multiple-pages.png "Это демонстрирует навигацию по кадрам между несколькими страницами.")

Не нужно использовать только <xref:System.Windows.Controls.Frame> внутри содержимого <xref:System.Windows.Controls.Page> . Также обычно размещается <xref:System.Windows.Controls.Frame> внутри содержимого <xref:System.Windows.Window> .

По умолчанию <xref:System.Windows.Controls.Frame> использует собственный журнал только в отсутствие другого журнала. Если <xref:System.Windows.Controls.Frame> компонент является частью содержимого, размещенного внутри <xref:System.Windows.Navigation.NavigationWindow> или XBAP, <xref:System.Windows.Controls.Frame> использует журнал, принадлежащий к <xref:System.Windows.Navigation.NavigationWindow> XBAP. Однако иногда <xref:System.Windows.Controls.Frame> может потребоваться ответственный за собственный журнал. Одной из причин для этого является разрешение навигации по журналам на страницах, размещенных в <xref:System.Windows.Controls.Frame> . Это показано на следующем рисунке.

![Схема фрейма и страницы](./media/navigation-overview/journal-navigation-within-pages-hosted-by-a-frame.png "Это показывает навигацию по журналам на страницах, размещенных в кадре.")

В этом случае можно настроить <xref:System.Windows.Controls.Frame> для использования собственного журнала, задав <xref:System.Windows.Controls.Frame.JournalOwnership%2A> для свойства объекта значение <xref:System.Windows.Controls.Frame> <xref:System.Windows.Navigation.JournalOwnership.OwnsJournal> . Это показано в следующем примере разметки.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]

На следующем рисунке показан результат перехода в <xref:System.Windows.Controls.Frame> , который использует собственный журнал.

![Фрейм с собственным журналом](./media/navigation-overview/frame-uses-its-own-journal.png "Это показывает результат перехода внутри фрейма, использующего собственный журнал.")

Обратите внимание, что записи журнала отображаются навигацией [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в <xref:System.Windows.Controls.Frame> , а не Internet Explorer.

> [!NOTE]
> Если <xref:System.Windows.Controls.Frame> компонент является частью содержимого, размещенного в <xref:System.Windows.Window> , <xref:System.Windows.Controls.Frame> использует собственный журнал и, следовательно, отображает собственную навигацию [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] .

Если взаимодействие с пользователем требуется <xref:System.Windows.Controls.Frame> для предоставления собственного журнала без отображения навигации [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , можно скрыть навигацию, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] задав для свойства значение <xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> <xref:System.Windows.Visibility.Hidden> . Это показано в следующем примере разметки.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]

<a name="Navigation_Hosts"></a>

## <a name="navigation-hosts"></a>Узлы переходов

<xref:System.Windows.Controls.Frame>и <xref:System.Windows.Navigation.NavigationWindow> являются классами, называемыми узлами навигации. *Узел навигации* — это класс, который может перейти к содержимому и отобразить его. Для этого каждый узел навигации использует собственные <xref:System.Windows.Navigation.NavigationService> журналы и. На следующем рисунке показана основная структура узла переходов.

![Схемы перехода](./media/navigation-overview/navigation-host-construction.png "Базовое создание узла навигации")

По сути, это позволяет <xref:System.Windows.Navigation.NavigationWindow> и <xref:System.Windows.Controls.Frame> предоставлять такую же поддержку навигации, которую предоставляет XBAP при размещении в браузере.

Помимо использования <xref:System.Windows.Navigation.NavigationService> и журнала, узлы навигации реализуют те же члены, которые <xref:System.Windows.Navigation.NavigationService> реализуют. Это показано на следующем рисунке.

![Журнал во фрейме и в NavigationWindow](./media/navigation-overview/navigation-window-and-frame.png "Окно навигации и фрейм")

Это позволяет программировать поддержку переходов непосредственно с ними. Это может быть полезно, если необходимо предоставить пользовательскую навигацию [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для <xref:System.Windows.Controls.Frame> , которая размещена в <xref:System.Windows.Window> . Более того, оба типа реализуют дополнительные элементы, связанные с навигацией, включая `BackStack` ( <xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType> , <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType> ) и `ForwardStack` ( <xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType> , <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType> ), которые позволяют перечислять записи журнала в стеке назад и в прямом стеке соответственно.

Как упоминалось ранее, в приложении может существовать несколько журналов. На следующем рисунке показано пример, когда это возможно.

![Несколько журналов в одном приложении](./media/navigation-overview/multiple-journals-in-one-application.png "Это пример более чем одного журнала в приложении.")

<a name="Navigating_to_Content_Other_than_Pages"></a>

## <a name="navigating-to-content-other-than-xaml-pages"></a>Переход к содержимому, отличному от страниц XAML

В этой статье <xref:System.Windows.Controls.Page> и пакетах XBAP использовались для демонстрации различных возможностей навигации WPF. Однако, <xref:System.Windows.Controls.Page> компилируемый в приложение, — это не единственный тип содержимого, к которому можно осуществлять переход, а пакет XBAP не единственный способ определить содержимое.

Как показано в этом разделе, можно также переходить к свободным [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файлам, ФАЙЛАМ HTML и объектам.

<a name="Navigating_to_Loose_XAML_Files"></a>

### <a name="navigating-to-loose-xaml-files"></a>Переход к свободным файлам XAML

Свободный [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл — это файл со следующими характеристиками:

- Содержит только [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (т. е. без кода).

- имеет объявление соответствующего пространства имен;

- имя файла имеет расширение XAML.

Например, рассмотрим следующее содержимое, которое хранится в виде свободного [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файла Person. XAML.

[!code-xaml[NavigationOverviewSnippets#LooseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]

Если дважды щелкнуть файл, браузер откроется, выполнит переход к содержимому и отобразит его. Это показано на следующем рисунке.

![Отображение содержимого в файле Person.XAML](./media/navigation-overview/contents-of-person-xaml-file.png "Отображает содержимое файла Person. XAML.")

Свободный файл можно вывести [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] из следующих файлов:

- веб-узел на локальном компьютере, в интрасети или Интернете;

- Общий файловый ресурс UNC.

- локальный диск.

Свободный [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл можно добавить в Избранное браузера или на домашнюю страницу браузера.

> [!NOTE]
> Дополнительные сведения о публикации и запуске свободных [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страниц см. [в разделе Развертывание приложения WPF](deploying-a-wpf-application-wpf.md).

Единственное ограничение в отношении свободного [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] : можно разместить только содержимое, которое может быть запущено в режиме частичного доверия. Например, `Window` не может быть корневым элементом свободного [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файла. Дополнительные сведения см. в разделе [Безопасность частичного доверия в WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_HTML_Files_Using_Frame"></a>

### <a name="navigating-to-html-files-by-using-frame"></a>Переход к файлам HTML элемента управления Frame

Как вы можете ожидать, можно также переходить к HTML. Необходимо просто предоставить универсальный код ресурса (URI), использующий схему HTTP. Например, ниже показано, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <xref:System.Windows.Controls.Frame> что выполняет переход на HTML-страницу.

[!code-xaml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]

Для перехода к HTML требуются специальные разрешения. Например, невозможно выполнить переход от XBAP, который выполняется в песочнице безопасности частичного доверия в зоне Интернета. Дополнительные сведения см. в разделе [Безопасность частичного доверия в WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>

### <a name="navigating-to-html-files-by-using-the-webbrowser-control"></a>Переход к файлам HTML с помощью элемента управления WebBrowser

<xref:System.Windows.Controls.WebBrowser>Элемент управления поддерживает размещение документов HTML, навигацию и взаимодействие сценариев и управляемого кода. Подробные сведения об <xref:System.Windows.Controls.WebBrowser> элементе управления см. в разделе <xref:System.Windows.Controls.WebBrowser> .

Как и при <xref:System.Windows.Controls.Frame> переходе на HTML с использованием, <xref:System.Windows.Controls.WebBrowser> требуются специальные разрешения. Например, из приложения с частичным доверием можно переходить только к HTML-коду, находящемуся на исходном узле. Дополнительные сведения см. в разделе [Безопасность частичного доверия в WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_Objects"></a>

### <a name="navigating-to-custom-objects"></a>Переход к пользовательским объектам

Если данные хранятся в виде пользовательских объектов, то один из способов отобразить эти данные — создать <xref:System.Windows.Controls.Page> с содержимым, привязанным к этим объектам (см. раздел [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)). Если не требуется создание всей страницы только для отображения объектов, то можно перейти непосредственно к ним.

Рассмотрим `Person` класс, реализованный в следующем коде.

[!code-csharp[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
[!code-vb[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]

Для перехода к нему вызывается <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType> метод, как показано в следующем коде.

[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]

[!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
[!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]

На рисунке ниже показан результат.

![Страница, осуществляющая переход в класс](./media/navigation-overview/page-navigates-to-an-object.png "Это пример страницы, которая выполняет переход к объекту.")

Из этого рисунка можно видеть, что ничего полезного не отобразилось. Фактически отображаемое значение является возвращаемым значением `ToString` метода для объекта **Person** ; по умолчанию это единственное значение, которое WPF может использовать для представления объекта. Можно переопределить `ToString` метод для возврата более значимой информации, хотя он все равно будет строковым значением. Один из способов, который позволяет использовать преимущества возможностей представления WPF, — использовать шаблон данных. Можно реализовать шаблон данных, который WPF может связать с объектом определенного типа. В следующем коде показан шаблон данных для `Person` объекта.

[!code-xaml[NavigateToObjectSnippets#DataTemplateMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]

Здесь шаблон данных связан с `Person` типом с помощью `x:Type` расширения разметки в `DataType` атрибуте. Затем шаблон данных привязывает `TextBlock` элементы (см <xref:System.Windows.Controls.TextBlock> .) к свойствам `Person` класса. На следующем рисунке показан обновленный внешний вид `Person` объекта.

![Переход к классу с шаблоном данных](./media/navigation-overview/navigating-to-a-class.png "Переход к классу, который содержит шаблон данных.")

Преимуществом этого способа является связность, которая обеспечивается возможностью повторного использования шаблона данных для согласованного отображения объектов в любом месте приложения.

Дополнительные сведения о шаблонах данных см. в разделе [Общие сведения о создании шаблонов данных](../data/data-templating-overview.md).

<a name="Security"></a>

## <a name="security"></a>Безопасность

Поддержка навигации в WPF позволяет переходить к XBAP через Интернет, что позволяет приложениям размещать сторонние материалы. Для защиты приложений и пользователей от вредоносного поведения WPF предоставляет разнообразные функции безопасности, обсуждаемые в разделе [Безопасность](../security-wpf.md) и [Безопасность частичного доверия в WPF](../wpf-partial-trust-security.md).

## <a name="see-also"></a>См. также

- <xref:System.Windows.Application.SetCookie%2A>
- <xref:System.Windows.Application.GetCookie%2A>
- [Общие сведения об управлении приложениями](application-management-overview.md)
- [URI типа "pack" в WPF](pack-uris-in-wpf.md)
- [Общие сведения о структурной навигации](structured-navigation-overview.md)
- [Общие сведения о топологии переходов](navigation-topologies-overview.md)
- [Практические руководства](navigation-how-to-topics.md)
- [Развертывание приложения WPF](deploying-a-wpf-application-wpf.md)
