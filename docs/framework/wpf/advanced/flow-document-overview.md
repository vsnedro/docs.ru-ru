---
title: Общие сведения о документах нефиксированного формата
description: Сведения о документах нефиксированного формата в Windows Presentation Foundation, которые динамически настраивают содержимое в зависимости от размера окна, разрешения устройства и настроек пользователя.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], flow documents [WPF], , '
- ', '
- flow documents [WPF]
ms.assetid: ef236a50-d44f-43c8-ba7c-82b0c733c0b7
ms.openlocfilehash: dac0cb91175a1398a0124020c048e14d7bcd1f76
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165234"
---
# <a name="flow-document-overview"></a>Общие сведения о документах нефиксированного формата

Документы нефиксированного формата предназначены для более удобного просмотра и чтения. Вместо того чтобы использовать какой-либо определенный макет, документы нефиксированного формата динамически корректируют и перемещают содержимое с учетом переменных времени выполнения, таких как размер окна, разрешение устройства и дополнительные пользовательские настройки. Кроме того, в документах нефиксированного формата доступны расширенные возможности, такие как разбивка на страницы и столбцы. В этом разделе представлены общие сведения о документах нефиксированного формата и способах их создания.

<a name="what_is_a_flow_document"></a>

## <a name="what-is-a-flow-document"></a>Что такое документ нефиксированного формата

Документ нефиксированного формата предназначен для "переформатирования содержимого" в зависимости от размера окна, разрешения устройства и других переменных среды. Кроме того, документы нефиксированного формата имеют несколько встроенных возможностей, включая поиск, режимы просмотра, оптимизирующие читаемость, и возможность менять размер и внешний вид шрифта. Документы нефиксированного формата следует использовать, если удобство чтения является основным приоритетом. Напротив, документы фиксированного формата предназначены для статического представления. Документы фиксированного формата полезны в тех случаях, когда важна точная передача содержимого источника. Дополнительные сведения о различных типах документов см. [в разделе документы в WPF](documents-in-wpf.md) .

Ниже показан образец документа нефиксированного формата, отображенного в нескольких окнах разных размеров. При изменении области отображения содержимое переформатируется для оптимального использования доступного пространства.

![Повторный поток содержимого документа нефиксированного формата](./media/edocs-flowdocument.png "eDocs_FlowDocument")

Как показано на рисунке выше, содержимое нефиксированного формата может включать многие компоненты, такие как абзацы, списки, изображения и др. Эти компоненты соответствуют элементам в разметке и объектам в процедурном коде. Более подробно эти классы будут рассмотрены далее в разделе [классы, связанные с потоками](#flow_related_classes) этого обзора. Сейчас вот простой пример кода, который создает документ нефиксированного формата, состоящий из абзаца с полужирным текстом и списком.

[!code-xaml[FlowOvwSnippets_snip#SimpleFlowExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SimpleFlowExample.xaml#simpleflowexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SimpleFlowExample.cs#simpleflowcodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SimpleFlowExample.vb#simpleflowcodeonlyexamplewholepage)]

На рисунке ниже представлен результат выполнения этого фрагмента кода.

![Снимок экрана: пример отображенного документа нефиксированного формата](./media/flow-ovw-first-example.png "Flow_Ovw_First_Example")

В этом примере <xref:System.Windows.Controls.FlowDocumentReader> элемент управления используется для размещения содержимого нефиксированного формата. Дополнительные сведения об элементах управления размещением содержимого нефиксированного формата см. в разделе [типы документов Flow](#flow_document_types) . <xref:System.Windows.Documents.Paragraph><xref:System.Windows.Documents.List>элементы,, <xref:System.Windows.Documents.ListItem> и <xref:System.Windows.Documents.Bold> используются для управления форматированием содержимого в зависимости от их порядка в разметке. Например, <xref:System.Windows.Documents.Bold> элемент охватывает только часть текста в абзаце; в результате только эта часть текста выделяется полужирным шрифтом. Если вы когда-либо работали с HTML, такой сценарий будет вам знаком.

Как видно на рисунке выше, в документах нефиксированного формата есть несколько встроенных функций:

- Поиск: позволяет пользователю выполнять полнотекстовый поиск по всему документу.

- Режим просмотра: пользователь может выбрать предпочтительный режим просмотра, включая постраничный (одна страница), двухстраничный (книжный формат чтения) и непрерывную прокрутку (документ без нижнего края).  Дополнительные сведения об этих режимах просмотра см. в разделе <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> .

- Элементы управления навигацией по страницам: если в режиме просмотра документа используются страницы, элементы управления перемещением по страницам включают кнопку для перехода на следующую страницу (стрелка вниз) или предыдущую страницу (стрелка вверх), а также индикаторы номера текущей страницы и общего числа страниц. Пролистывание страниц может также выполняться с помощью клавиши со стрелками.

- Увеличение: элементы управления масштабом позволяют пользователю увеличить или уменьшить масштаб, нажав кнопку "плюс" или "минус", соответственно. Элементы управления масштабом также включают ползунок для изменения масштаба. Для получения дополнительной информации см. <xref:System.Windows.Controls.FlowDocumentReader.Zoom%2A>.

Эти функции можно изменять с учетом элемента управления, используемого для размещения содержимого. В следующем разделе описываются различные элементы управления.

<a name="flow_document_types"></a>

## <a name="flow-document-types"></a>Типы документов нефиксированного формата

Отображение содержимого документа нефиксированного формата и его вид зависят от того, какой объект используется для размещения содержимого. Существует четыре элемента управления, поддерживающих просмотр содержимого нефиксированного формата: <xref:System.Windows.Controls.FlowDocumentReader> , <xref:System.Windows.Controls.FlowDocumentPageViewer> , <xref:System.Windows.Controls.RichTextBox> и <xref:System.Windows.Controls.FlowDocumentScrollViewer> . Эти элементы управления кратко описаны ниже.

> [!NOTE]
> <xref:System.Windows.Documents.FlowDocument>требуется для непосредственного размещения содержимого нефиксированного формата, поэтому все эти элементы управления просмотра используют <xref:System.Windows.Documents.FlowDocument> для включения размещения содержимого нефиксированного формата.

### <a name="flowdocumentreader"></a>FlowDocumentReader

<xref:System.Windows.Controls.FlowDocumentReader>включает функции, позволяющие пользователю динамически выбирать между различными режимами просмотра, включая одностраничный (страничный) режим просмотра, два страничных режима (формат чтения книги) и непрерывный режим просмотра (без нижнего прокрутки). Дополнительные сведения об этих режимах просмотра см. в разделе <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> . Если не требуется возможность динамически переключаться между разными режимами просмотра <xref:System.Windows.Controls.FlowDocumentPageViewer> и <xref:System.Windows.Controls.FlowDocumentScrollViewer> предоставить облегченные средства просмотра содержимого нефиксированного формата, исправленные в определенном режиме просмотра.

### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer и FlowDocumentScrollViewer

<xref:System.Windows.Controls.FlowDocumentPageViewer>показывает содержимое в режиме просмотра на странице, в то время как <xref:System.Windows.Controls.FlowDocumentScrollViewer> отображает содержимое в режиме непрерывной прокрутки. <xref:System.Windows.Controls.FlowDocumentPageViewer>И, и исправляются <xref:System.Windows.Controls.FlowDocumentScrollViewer> в определенный режим просмотра. Сравните с <xref:System.Windows.Controls.FlowDocumentReader> , который включает функции, позволяющие пользователю динамически выбирать между различными режимами просмотра (в соответствии с <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> перечислением), за счет более ресурсоемких ресурсов, чем <xref:System.Windows.Controls.FlowDocumentPageViewer> или <xref:System.Windows.Controls.FlowDocumentScrollViewer> .

По умолчанию вертикальная полоса прокрутки отображается всегда, а горизонтальная полоса прокрутки становится видимой при необходимости. Пользовательский интерфейс по умолчанию для не <xref:System.Windows.Controls.FlowDocumentScrollViewer> включает панель инструментов, однако <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> свойство можно использовать для включения встроенной панели инструментов.

### <a name="richtextbox"></a>RichTextBox

Используйте, <xref:System.Windows.Controls.RichTextBox> Если вы хотите разрешить пользователю изменять содержимое нефиксированного формата. Например, если вы хотите создать редактор, который позволял бы пользователю манипулировать такими элементами, как таблицы, курсивом и полужирным шрифтом и т. д., следует использовать <xref:System.Windows.Controls.RichTextBox> . Дополнительные сведения см. в [обзоре RichTextBox](../controls/richtextbox-overview.md) .

> [!NOTE]
> Содержимое нефиксированного формата внутри не работает точно так же, <xref:System.Windows.Controls.RichTextBox> как и содержимое потока, содержащееся в других элементах управления. Например, отсутствуют столбцы в и, следовательно, <xref:System.Windows.Controls.RichTextBox> Автоматическое изменение размера не выполняется. Кроме того, обычно встроенные функции содержимого нефиксированного формата, такие как поиск, режим просмотра, Навигация по страницам и масштаб, недоступны в <xref:System.Windows.Controls.RichTextBox> .

<a name="creating_flow_content"></a>

## <a name="creating-flow-content"></a>Создание содержимого нефиксированного формата

Содержимое нефиксированного формата может быть сложным, состоящим из различных элементов, включая текст, изображения, таблицы и даже <xref:System.Windows.UIElement> производные классы, такие как элементы управления. Чтобы понять, как создавать сложное размещение содержимого, нужно учитывать следующее:

- **Классы, связанные с размещением содержимого**: каждый класс, используемый в содержимом нефиксированного формата, имеет особое назначение. Кроме того, иерархическая связь между классами нефиксированного формата помогает понять, как они используются. Например, классы, производные от <xref:System.Windows.Documents.Block> класса, используются для хранения других объектов, в то время как классы, производные от <xref:System.Windows.Documents.Inline> , содержат объекты, которые отображаются.

- **Схема содержимого**: документ нефиксированного формата может потребовать значительного числа вложенных элементов. Схема содержимого задает возможные отношения типа "родительский-дочерний" между элементами.

В следующих разделах все эти вопросы будут рассмотрены более подробно.

<a name="flow_related_classes"></a>

## <a name="flow-related-classes"></a>Классы, связанные с содержимым нефиксированного формата

На приведенной ниже схеме показаны объекты, которые чаще всего используется с содержимым нефиксированного формата:

![Схема: иерархия класса элемента потока содержимого](./media/flow-class-hierarchy.png "Flow_Class_Hierarchy")

В работе с размещением содержимого используются две важные категории:

1. **Классы, производные от блока**: также называются "блоковыми элементами содержимого" или просто "блоковыми элементами". Элементы, наследующие от, <xref:System.Windows.Documents.Block> могут использоваться для группирования элементов в общем родительском объекте или для применения общих атрибутов к группе.

2. **Встроенные производные классы**: также называются "встроенными элементами содержимого" или просто "встроенными элементами". Элементы, наследующие от <xref:System.Windows.Documents.Inline> , либо содержатся в элементе Block, либо в другом встроенном элементе. Встроенные элементы часто используются в качестве непосредственного контейнера содержимого, отображаемого на экране. Например, <xref:System.Windows.Documents.Paragraph> (блочный элемент) может содержать <xref:System.Windows.Documents.Run> (встроенный элемент), но <xref:System.Windows.Documents.Run> фактически содержит текст, отображаемый на экране.

Ниже кратко описан каждый класс этих категорий.

### <a name="block-derived-classes"></a>Классы, производные от блока

**Интервал**

<xref:System.Windows.Documents.Paragraph>обычно используется для группирования содержимого в абзац. Самый простой и распространенный способ использования класса Paragraph — составление текстового абзаца.

[!code-xaml[FlowOvwSnippets_snip#ParagraphExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ParagraphExample.xaml#paragraphexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ParagraphExample.cs#paragraphcodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ParagraphExample.vb#paragraphcodeonlyexamplewholepage)]

Однако можно также включить другие элементы, производные от встроенного кода, как показано ниже.

**Раздел**

<xref:System.Windows.Documents.Section>используется только для хранения других <xref:System.Windows.Documents.Block> элементов, производных от. Он не применяет никакого форматирования по умолчанию к содержащимся в нем элементам. Однако все значения свойств, заданные для, <xref:System.Windows.Documents.Section> применяются к его дочерним элементам. Раздел также позволяет программным способом перебирать свою дочернюю коллекцию. <xref:System.Windows.Documents.Section>используется аналогичным образом для \<DIV> тега в HTML.

В приведенном ниже примере в одном из них определены три абзаца <xref:System.Windows.Documents.Section> . Раздел имеет свойство со <xref:System.Windows.Documents.TextElement.Background%2A> значением Red, поэтому цвет фона абзацев также красный.

[!code-xaml[FlowOvwSnippets_snip#SectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SectionExample.xaml#sectionexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SectionExample.cs#sectioncodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SectionExample.vb#sectioncodeonlyexamplewholepage)]

**BlockUIContainer**

<xref:System.Windows.Documents.BlockUIContainer>позволяет <xref:System.Windows.UIElement> внедрять элементы (т. е. <xref:System.Windows.Controls.Button> ) в содержимое потока, производное от блока. <xref:System.Windows.Documents.InlineUIContainer>(см. ниже) используется для внедрения <xref:System.Windows.UIElement> элементов во встроенное содержимое потока. <xref:System.Windows.Documents.BlockUIContainer>и <xref:System.Windows.Documents.InlineUIContainer> важны, поскольку нет другого способа использовать <xref:System.Windows.UIElement> в нефиксированном содержимом, если он не содержится в одном из этих двух элементов.

В следующем примере показано, как использовать <xref:System.Windows.Documents.BlockUIContainer> элемент для размещения <xref:System.Windows.UIElement> объектов в содержимом нефиксированного формата.

[!code-xaml[SpanSnippets#_BlockUIXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml#_blockuixaml)]

На следующем рисунке показано, как отображается этот пример.

![Снимок экрана, показывающий UIElement, внедренный в нефиксированное содержимое.](./media/flow-document-overview/embedded-blockuicontainer.png)

**Список**

<xref:System.Windows.Documents.List>используется для создания маркированного или нумерованного списка. Присвойте <xref:System.Windows.Documents.List.MarkerStyle%2A> свойству <xref:System.Windows.TextMarkerStyle> значение перечисления, чтобы определить стиль списка. В приведенном ниже примере показано, как создать простой список.

[!code-xaml[FlowOvwSnippets_snip#ListExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ListExample.xaml#listexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ListExample.cs#listcodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ListExample.vb#listcodeonlyexamplewholepage)]

> [!NOTE]
> <xref:System.Windows.Documents.List>— Это единственный элемент Flow, использующий <xref:System.Windows.Documents.ListItemCollection> для управления дочерними элементами.

**Таблица**

<xref:System.Windows.Documents.Table>используется для создания таблицы. <xref:System.Windows.Documents.Table>функция похожа на <xref:System.Windows.Controls.Grid> элемент, но имеет больше возможностей и, следовательно, требует большего объема ресурсов. Поскольку <xref:System.Windows.Controls.Grid> является <xref:System.Windows.UIElement> , он не может использоваться в потоке содержимого, если он не содержится в <xref:System.Windows.Documents.BlockUIContainer> или <xref:System.Windows.Documents.InlineUIContainer> . Дополнительные сведения о см <xref:System.Windows.Documents.Table> . в разделе [Общие сведения о таблице](table-overview.md).

### <a name="inline-derived-classes"></a>Встроенные классы

**Выполнить**

<xref:System.Windows.Documents.Run>используется для хранения неформатированного текста. Вы можете ожидать, что <xref:System.Windows.Documents.Run> объекты будут широко использоваться в содержимом нефиксированного формата. Однако в разметке <xref:System.Windows.Documents.Run> элементы не обязательно должны использоваться явным образом. <xref:System.Windows.Documents.Run>необходимо использовать при создании документов нефиксированного формата или управлении ими с помощью кода. Например, в разметке, приведенной ниже, первый <xref:System.Windows.Documents.Paragraph> указывает <xref:System.Windows.Documents.Run> элемент явным образом, а второй — нет. Оба абзаца создают идентичные выходные данные.

[!code-xaml[FlowOvwSnippets_snip#RunExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/RunSnippetsExample.xaml#runexample1)]

> [!NOTE]
> Начиная с .NET Framework 4, <xref:System.Windows.Documents.Run.Text%2A> свойство <xref:System.Windows.Documents.Run> объекта является свойством зависимостей. Можно привязать <xref:System.Windows.Documents.Run.Text%2A> свойство к источнику данных, например к <xref:System.Windows.Controls.TextBlock> . <xref:System.Windows.Documents.Run.Text%2A>Свойство полностью поддерживает одностороннюю привязку. <xref:System.Windows.Documents.Run.Text%2A>Свойство также поддерживает двустороннюю привязку, за исключением <xref:System.Windows.Controls.RichTextBox> . Пример см. в разделе <xref:System.Windows.Documents.Run.Text%2A?displayProperty=nameWithType>.

**Размещать**

<xref:System.Windows.Documents.Span>группирует другие встроенные элементы содержимого вместе. К содержимому внутри элемента не применяется встроенная отрисовка <xref:System.Windows.Documents.Span> . Однако элементы, унаследованные от <xref:System.Windows.Documents.Span> <xref:System.Windows.Documents.Hyperlink> , включают, <xref:System.Windows.Documents.Bold> и, <xref:System.Windows.Documents.Italic> <xref:System.Windows.Documents.Underline> применяют форматирование к тексту.

Ниже приведен пример <xref:System.Windows.Documents.Span> использования для включения встроенного содержимого, включая текст, <xref:System.Windows.Documents.Bold> элемент и <xref:System.Windows.Controls.Button> .

[!code-xaml[FlowOvwSnippets_snip#SpanExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SpanExample.xaml#spanexamplewholepage)]

На следующем снимке экрана показана отрисовка этого примера.

![Снимок экрана: пример отображенного элемента Span](./media/flow-spanexample.gif "Flow_SpanExample")

**InlineUIContainer**

<xref:System.Windows.Documents.InlineUIContainer>позволяет <xref:System.Windows.UIElement> внедрять элементы (например, элемент управления <xref:System.Windows.Controls.Button> ) в <xref:System.Windows.Documents.Inline> элемент содержимого. Этот элемент является встроенным эквивалентом, <xref:System.Windows.Documents.BlockUIContainer> описанным выше. Ниже приведен пример использования <xref:System.Windows.Documents.InlineUIContainer> для вставки <xref:System.Windows.Controls.Button> встроенного элемента в <xref:System.Windows.Documents.Paragraph> .

[!code-xaml[FlowOvwSnippets_snip#InlineUIContainerExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/InlineUIContainerExample.xaml#inlineuicontainerexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/InlineUIContainerExample.cs#inlineuicontainercodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/InlineUIContainerExample.vb#inlineuicontainercodeonlyexamplewholepage)]

> [!NOTE]
> <xref:System.Windows.Documents.InlineUIContainer>не нужно явно использовать в разметке. Если опустить его, <xref:System.Windows.Documents.InlineUIContainer> будет создано исключение при компиляции кода.

**Figure и Floater**

<xref:System.Windows.Documents.Figure>и <xref:System.Windows.Documents.Floater> используются для внедрения содержимого в документы нефиксированного формата со свойствами размещения, которые могут быть настроены независимо от основного потока содержимого. <xref:System.Windows.Documents.Figure><xref:System.Windows.Documents.Floater>элементы или часто используются для выделения или акцентирования частей содержимого, для размещения вспомогательных изображений или другого содержимого в основном потоке содержимого или для вставки слабо связанного содержимого, такого как объявления.

В следующем примере показано, как внедрить <xref:System.Windows.Documents.Figure> в абзац текста.

[!code-xaml[FlowOvwSnippets_snip#FigureExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/FigureExample.xaml#figureexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/FigureExample.cs#figurecodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/FigureExample.vb#figurecodeonlyexamplewholepage)]

На рисунке ниже показано, как будет выглядеть этот пример.

![Снимок экрана: пример фигуры](./media/flow-ovw-figure-example.png "Flow_Ovw_Figure_Example")

<xref:System.Windows.Documents.Figure>и <xref:System.Windows.Documents.Floater> различаются несколькими способами и используются для различных сценариев.

**Замкнут**

- Можно указывать местоположение: с помощью горизонтальных и вертикальных якорей можно закрепить элемент относительно страницы. содержимого, столбца или абзаца. Также можно использовать <xref:System.Windows.Documents.Figure.HorizontalOffset%2A> <xref:System.Windows.Documents.Figure.VerticalOffset%2A> Свойства и для указания произвольных смещений.

- Может иметь размер более чем для одного столбца: можно задать <xref:System.Windows.Documents.Figure> высоту и ширину для множества страниц, содержимого, высоты или ширины столбцов. Обратите внимание, что в случае страницы и содержимого кратность более 1 не поддерживается. Например, можно задать ширину a <xref:System.Windows.Documents.Figure> равную «0,5 Page» или «0,25» или «2 столбца». Также можно задать высоту и ширину в абсолютных пиксельных значениях.

- Не выполняется разбиение на страницы: Если содержимое внутри не <xref:System.Windows.Documents.Figure> помещается в <xref:System.Windows.Documents.Figure> , будет отображаться любое содержимое, которое не умещается, а оставшееся содержимое будет потеряно.

**Floater:**

- Невозможно указать местоположение, отрисовывается в любом доступном пространстве. Нельзя задать смещение или привязку a <xref:System.Windows.Documents.Floater> .

- Не может иметь размер более чем для одного столбца: по умолчанию <xref:System.Windows.Documents.Floater> размеры находятся в одном столбце. Он имеет <xref:System.Windows.Documents.Floater.Width%2A> свойство, которому можно присвоить абсолютное значение в пикселях, но если это значение больше, чем одна ширина столбца, оно игнорируется, а размер плавающего объекта изменяется на один столбец. Его можно сделать менее чем одним столбцом, установив правильную ширину в пикселях, но при этом размер не должен относиться к столбцам, поэтому "0,5 Column" не является допустимым выражением для <xref:System.Windows.Documents.Floater> ширины. <xref:System.Windows.Documents.Floater>не имеет свойства высоты и не может быть задана высота, ее высота зависит от содержимого

- <xref:System.Windows.Documents.Floater>Разбиение: если его содержимое с заданной шириной увеличено до 1 высоты столбца, плавающий элемент прерывает и разбиение к следующему столбцу, следующей странице и т. д.

 <xref:System.Windows.Documents.Figure>является хорошим местом для размещения автономного содержимого, в котором требуется управлять размером и положением, и уверенным в том, что содержимое будет помещаться в указанный размер. <xref:System.Windows.Documents.Floater>— хорошее место для размещения более свободного содержимого, которое напоминает содержимое главной страницы, но отделяется от него.

**LineBreak**

<xref:System.Windows.Documents.LineBreak>вызывает разрыв строки в содержимом нефиксированного формата. В следующем примере показано использование функции <xref:System.Windows.Documents.LineBreak>.

[!code-xaml[FlowOvwSnippets_snip#LineBreakExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/LineBreakExample.xaml#linebreakexamplewholepage)]

На следующем снимке экрана показана отрисовка этого примера.

![Снимок экрана: пример LineBreak](./media/flow-ovw-linebreakexample.png "Flow_Ovw_LineBreakExample")

### <a name="flow-collection-elements"></a>Элементы коллекции нефиксированного формата

Во многих примерах, приведенных выше, <xref:System.Windows.Documents.BlockCollection> и <xref:System.Windows.Documents.InlineCollection> используются для создания содержимого нефиксированного формата программным образом. Например, чтобы добавить элементы в <xref:System.Windows.Documents.Paragraph> , можно использовать синтаксис:

```csharp
myParagraph.Inlines.Add(new Run("Some text"));
```

При этом добавляется <xref:System.Windows.Documents.Run> в <xref:System.Windows.Documents.InlineCollection> коллекцию <xref:System.Windows.Documents.Paragraph> .  Это аналогично неявному <xref:System.Windows.Documents.Run> обнаружению <xref:System.Windows.Documents.Paragraph> в разметке:

```xml
<Paragraph>
Some Text
</Paragraph>
```

В качестве примера использования <xref:System.Windows.Documents.BlockCollection> , приведенный ниже пример создает новый объект <xref:System.Windows.Documents.Section> , а затем использует метод **Add** , чтобы добавить новый объект <xref:System.Windows.Documents.Paragraph> к <xref:System.Windows.Documents.Section> содержимому.

[!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
[!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]

Помимо добавления элементов в коллекцию нефиксированного формата элементы также можно удалять.  В следующем примере удаляется последний <xref:System.Windows.Documents.Inline> элемент в <xref:System.Windows.Documents.Span> .

[!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
[!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]

В следующем примере удаляется все содержимое ( <xref:System.Windows.Documents.Inline> элементы) из <xref:System.Windows.Documents.Span> .

[!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
[!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]

При работе с содержимым нефиксированного формата программными средствами эти коллекции, скорее всего, будут использоваться довольно активно.

Использует ли элемент Flow <xref:System.Windows.Documents.InlineCollection> (Inlines) или <xref:System.Windows.Documents.BlockCollection> (Blocks) для хранения своих дочерних элементов, зависит от того, какой тип дочерних элементов ( <xref:System.Windows.Documents.Block> или <xref:System.Windows.Documents.Inline> ) может содержаться в родительском элементе. Правила включения для элементов размещения содержимого обобщаются в схеме содержимого в следующем разделе.

> [!NOTE]
> Существует третий тип коллекции, используемый с содержимым нефиксированного формата, <xref:System.Windows.Documents.ListItemCollection> но эта коллекция используется только с <xref:System.Windows.Documents.List> . Кроме того, существует несколько коллекций, используемых с <xref:System.Windows.Documents.Table> . Дополнительные сведения см. в разделе [Общие сведения о таблице](table-overview.md) .

<a name="content_schema"></a>

## <a name="content-schema"></a>Схема содержимого

Учитывая количество различных элементов в документах нефиксированного формата, может быть очень сложно отследить, какой тип дочерних элементов может содержать тот или иной элемент. На схеме ниже представлены правила включения для элементов нефиксированного формата. Стрелки указывают возможные связи "родитель-потомок".

![Схема: схема вместимости потока содержимого](./media/flow-content-schema.png "Flow_Content_Schema")

Как видно из приведенной выше схемы, дочерние элементы, разрешенные для элемента, не обязательно определяются тем, является ли он <xref:System.Windows.Documents.Block> элементом или <xref:System.Windows.Documents.Inline> элементом. Например, <xref:System.Windows.Documents.Span> <xref:System.Windows.Documents.Inline> элемент (element) может иметь только <xref:System.Windows.Documents.Inline> дочерние элементы, тогда как <xref:System.Windows.Documents.Figure> (также <xref:System.Windows.Documents.Inline> элемент) может иметь только <xref:System.Windows.Documents.Block> дочерние элементы. Таким образом, схему можно использовать для быстрого определения элемента, который может содержаться в другом элементе. В качестве примера рассмотрим схему, чтобы определить, как создать содержимое нефиксированного формата <xref:System.Windows.Controls.RichTextBox> .

**1.** объект <xref:System.Windows.Controls.RichTextBox> должен содержать, <xref:System.Windows.Documents.FlowDocument> который, в свою очередь, должен содержать <xref:System.Windows.Documents.Block> объект, производный от. Ниже приведен соответствующий сегмент из предыдущей диаграммы.

![Схема: правила вместимости RichTextBox](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")

Разметка может выглядеть следующим образом.

[!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]

**2.** в соответствии с диаграммой существует несколько элементов, которые можно <xref:System.Windows.Documents.Block> выбрать, включая <xref:System.Windows.Documents.Paragraph> , <xref:System.Windows.Documents.Section> , <xref:System.Windows.Documents.Table> , <xref:System.Windows.Documents.List> и <xref:System.Windows.Documents.BlockUIContainer> (см. раздел классы, производные от блока). Предположим, нам нужно <xref:System.Windows.Documents.Table> . В соответствии с приведенной выше схемой <xref:System.Windows.Documents.Table> содержит <xref:System.Windows.Documents.TableRowGroup> <xref:System.Windows.Documents.TableRow> элементы, содержащие элементы, <xref:System.Windows.Documents.TableCell> которые содержат объект, <xref:System.Windows.Documents.Block> производный от. Ниже приведен соответствующий сегмент, <xref:System.Windows.Documents.Table> взятый из диаграммы выше.

![Схема: Родительская Дочерняя схема&#47;для таблицы](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")

Ниже приводится соответствующая разметка.

[!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]

**3.** опять же, один или несколько <xref:System.Windows.Documents.Block> элементов должны находиться под <xref:System.Windows.Documents.TableCell> . Для удобства поместим часть текста в ячейку. Это можно сделать с помощью <xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Documents.Run> элемента. Ниже приводятся соответствующие сегменты из схемы, показывающие, что <xref:System.Windows.Documents.Paragraph> может принимать <xref:System.Windows.Documents.Inline> элемент и что <xref:System.Windows.Documents.Run> ( <xref:System.Windows.Documents.Inline> элемент) может принимать только обычный текст.

![Схема: родительская&#47;дочерняя схема для абзаца](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")

![Схема: Родительская Дочерняя схема&#47;для запуска](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")

Ниже приведен полный пример в виде разметки.

[!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]

<a name="customizing_text"></a>

## <a name="customizing-text"></a>Настройка текста

Обычно текст является наиболее распространенным типом содержимого в документе нефиксированного формата. Хотя представленные выше объекты могут использоваться для управления большинством аспектов отображения текста, существуют и другие методы для настройки текста, описанные в этом разделе.

### <a name="text-decorations"></a>Оформление текста

Оформление текста позволяет применять к тексту эффекты подчеркивания, надчеркивания, нижней линии и зачеркивания (см. рисунки ниже). Эти украшения добавляются с помощью <xref:System.Windows.Documents.Inline.TextDecorations%2A> свойства, предоставляемого несколькими объектами, включая <xref:System.Windows.Documents.Inline> , <xref:System.Windows.Documents.Paragraph> , <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Controls.TextBox> .

В следующем примере показано, как задать свойство <xref:System.Windows.Documents.Paragraph.TextDecorations%2A> объекта <xref:System.Windows.Documents.Paragraph>.

[!code-xaml[InlineSnippets#_Paragraph_TextDecXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml#_paragraph_textdecxaml)]

[!code-csharp[InlineSnippets#_Paragraph_TextDec](~/samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml.cs#_paragraph_textdec)]
[!code-vb[InlineSnippets#_Paragraph_TextDec](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InlineSnippets/visualbasic/window1.xaml.vb#_paragraph_textdec)]

На следующем рисунке показано, как этот пример отрисовывается.

![Снимок экрана: текст с эффектом зачеркивания по умолчанию](./media/inline-textdec-strike.png "Inline_TextDec_Strike")

На следующих рисунках показано, как выводятся элементы назначений « **линия**», « **Базовая линия**» и « **Подчеркивание** » соответственно.

![Снимок экрана: надстрочный TextDecorator](./media/inline-textdec-over.png "Inline_TextDec_Over")

![Снимок экрана: эффект базового плана для текста по умолчанию](./media/inline-textdec-base.png "Inline_TextDec_Base")

![Снимок экрана: текст с эффектом подчеркивания по умолчанию](./media/inline-textdec-under.png "Inline_TextDec_Under")

### <a name="typography"></a>Шрифтовое оформление

<xref:System.Windows.Documents.TextElement.Typography%2A>Свойство предоставляется большинством связанных с потоком содержимого, включая <xref:System.Windows.Documents.TextElement> ,, <xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Controls.TextBox> . Это свойство используется для управления типографскими характеристиками текста (т. е. малыми прописными или строчными буквами, надстрочными и подстрочными символами и т. д.).

В следующем примере показано, как задать <xref:System.Windows.Documents.TextElement.Typography%2A> атрибут, используя в <xref:System.Windows.Documents.Paragraph> качестве элемента example.

[!code-xaml[TextElementSnippets#_TextElement_TypogXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]

На следующем рисунке показано, как этот пример отрисовывается.

![Снимок экрана: текст с измененной типографией](./media/textelement-typog.png "TextElement_Typog")

Напротив, на следующем рисунке показано, как отрисовывается аналогичный пример с типографскими характеристиками по умолчанию.

![Снимок экрана: текст с измененной типографией](./media/textelement-typog-default.png "TextElement_Typog_Default")

В следующем примере показано, как задать <xref:System.Windows.Controls.TextBox.Typography%2A> свойство программным способом.

[!code-csharp[TextElementSnippets#_TextElement_Typog](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
[!code-vb[TextElementSnippets#_TextElement_Typog](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]

Дополнительные сведения о типографском оформлении см. [в разделе типографские в WPF](typography-in-wpf.md) .

## <a name="see-also"></a>См. также

- [Текст](optimizing-performance-text.md)
- [Оформление в WPF](typography-in-wpf.md)
- [Практические руководства](flow-content-elements-how-to-topics.md)
- [Общие сведения о модели содержимого TextElement](textelement-content-model-overview.md)
- [Общие сведения о RichTextBox](../controls/richtextbox-overview.md)
- [Документы в WPF](documents-in-wpf.md)
- [Общие сведения о таблицах](table-overview.md)
- [Общие сведения о заметках](annotations-overview.md)
