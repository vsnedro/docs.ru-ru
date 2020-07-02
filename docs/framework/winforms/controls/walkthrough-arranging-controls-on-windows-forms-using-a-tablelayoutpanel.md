---
title: Упорядочение элементов управления с помощью TableLayoutPanel
description: Сведения о том, как упорядочивать элементы управления в Windows Forms с помощью элемента управления FlowLayoutPanel и элемента управления TableLayoutPanel.
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with TableLayoutPanel
- TableLayoutPanel control [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
ms.openlocfilehash: 6dfc6dbdef38d635dc94877f79a8e3659295bd98
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622800"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel"></a>Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel

В некоторых приложениях требуется форма, макет которой изменяется надлежащим образом при изменении размера формы или содержимого. Если необходим динамический макет и вы не хотите обрабатывать события <xref:System.Windows.Forms.Control.Layout> явно в коде, рассмотрите возможность использования панели макета.

Элементы управления <xref:System.Windows.Forms.FlowLayoutPanel> и <xref:System.Windows.Forms.TableLayoutPanel> предоставляют удобные способы упорядочения элементов управления в форме. Они обеспечивают автоматическую настраиваемую возможность управления относительным положением содержащихся в них дочерних элементов управления и предоставляют функции динамического макета во время выполнения и таким образом могут изменять размер и положение дочерних элементов управления по мере измерения размеров родительской формы. Панели макета могут быть вложенными в других панелях макета, что позволяет реализовывать сложные пользовательские интерфейсы.

Элемент управления <xref:System.Windows.Forms.FlowLayoutPanel> упорядочивает свое содержимое в определенном направлении, горизонтальном или вертикальном. Его содержимое может быть перенесено из одной строки в следующую или из одного столбца в следующий. Кроме того, вместо переноса содержимое может обрезаться. Дополнительные сведения см. [в разделе Пошаговое руководство. Упорядочивание элементов управления в Windows Forms с помощью элемента FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).

<xref:System.Windows.Forms.TableLayoutPanel>Компонент упорядочивает свое содержимое в сетке, предоставляя функциональные возможности, аналогичные HTML- \<table> элементу. <xref:System.Windows.Forms.TableLayoutPanel>Элемент управления позволяет размещать элементы управления в макете сетки без необходимости точного указания положения каждого отдельного элемента управления. Его ячейки организованы в строки и столбцы, и они могут быть разного размера. Ячейки можно объединять между строками и столбцами. Ячейки могут содержать все, что может содержать форма, и вести себя в других отношениях в качестве контейнеров.

Этот <xref:System.Windows.Forms.TableLayoutPanel> элемент управления также предоставляет возможность пропорционального изменения размера во время выполнения, поэтому макет может плавно меняться по мере изменения размера формы. Это делает <xref:System.Windows.Forms.TableLayoutPanel> элемент управления хорошо подходящим для таких целей, как формы ввода данных и локализованные приложения. Дополнительные сведения см. в разделе [Пошаговое руководство. Создание формы Windows с изменяемым размером для ввода данных](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)) и [Пошаговое руководство. Создание локализуемых форм Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).

В общем случае не следует использовать <xref:System.Windows.Forms.TableLayoutPanel> элемент управления в качестве контейнера для всего макета. Используйте <xref:System.Windows.Forms.TableLayoutPanel> элементы управления, чтобы обеспечить пропорциональные возможности изменения размера для частей макета.

В данном пошаговом руководстве представлены следующие задачи.

- Создание проекта Windows Forms

- Упорядочение элементов управления в строках и столбцах

- Установка свойств строк и столбцов

- Объединение строк и столбцов с помощью элемента управления

- Автоматическая обработка перегрузок

- Вставка элементов управления двойным щелчком по ним в панели элементов

- Вставка элемента управления путем рисования его контура

- Переназначение существующих элементов управления другим родительским элементам

После завершения вы будете понимать роль, которую играют эти важные функции макета.

## <a name="creating-the-project"></a>Создание проекта

Первым шагом является создание проекта и настройка формы.

#### <a name="to-create-the-project"></a>Создание проекта

1. Создайте проект приложения Windows с именем "Таблелайаутпанелексампле". Дополнительные сведения см. [в разделе инструкции. Создание проекта Windows Forms приложения](/visualstudio/ide/step-1-create-a-windows-forms-application-project) .

2. Выберите форму в конструкторе **Windows** **Forms**.

## <a name="arranging-controls-in-rows-and-columns"></a>Упорядочение элементов управления в строках и столбцах

<xref:System.Windows.Forms.TableLayoutPanel>Элемент управления позволяет легко упорядочивать элементы управления по строкам и столбцам.

#### <a name="to-arrange-controls-in-rows-and-columns-using-a-tablelayoutpanel"></a>Размещение элементов управления в строках и столбцах с помощью TableLayoutPanel

1. Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму. Обратите внимание, что по умолчанию <xref:System.Windows.Forms.TableLayoutPanel> элемент управления содержит четыре ячейки.

2. Перетащите <xref:System.Windows.Forms.Button> элемент управления из **панели элементов** в <xref:System.Windows.Forms.TableLayoutPanel> элемент управления и поместите его в одну из ячеек. Обратите внимание, что <xref:System.Windows.Forms.Button> элемент управления создается в выбранной ячейке.

3. Перетащите еще три <xref:System.Windows.Forms.Button> элемента управления из **панели элементов** в <xref:System.Windows.Forms.TableLayoutPanel> элемент управления, чтобы каждая ячейка содержала кнопку.

4. Возьмите вертикальный маркер изменения размера между двумя столбцами и переместите его влево. Обратите внимание, что <xref:System.Windows.Forms.Button> размеры элементов управления в первом столбце изменяются до меньшей ширины, а размер <xref:System.Windows.Forms.Button> элементов управления во втором столбце не изменяется.

5. Возьмите вертикальный маркер изменения размера между двумя столбцами и переместите его вправо. Обратите внимание, что <xref:System.Windows.Forms.Button> элементы управления в первом столбце возвращают исходный размер, а <xref:System.Windows.Forms.Button> элементы управления во втором столбце перемещаются вправо.

6. Переместите горизонтальный маркер изменения размера вверх и вниз, чтобы увидеть воздействие на элементы управления на панели.

## <a name="positioning-controls-within-cells-using-docking-and-anchoring"></a>Размещение элементов управления внутри ячеек с помощью закрепления и привязки

Поведение привязки дочерних элементов управления в <xref:System.Windows.Forms.TableLayoutPanel> отличается от поведения в других контейнерных элементах управления. Поведение закрепления дочерних элементов управления аналогично поведению других элементов управления контейнера.

#### <a name="positioning-controls-within-cells"></a>Размещение элементов управления внутри ячеек

1. Выберите первый <xref:System.Windows.Forms.Button> элемент управления. Измените значение его свойства <xref:System.Windows.Forms.Control.Dock%2A> на <xref:System.Windows.Forms.DockStyle.Fill>. Обратите внимание, что <xref:System.Windows.Forms.Button> элемент управления разворачивается для заполнения ячейки.

2. Выберите один из других <xref:System.Windows.Forms.Button> элементов управления. Измените значение его свойства <xref:System.Windows.Forms.Control.Anchor%2A> на <xref:System.Windows.Forms.AnchorStyles.Right>. Обратите внимание, что она перемещается таким образом, что правая граница находится ближе к правой границе ячейки. Расстояние между границами является суммой <xref:System.Windows.Forms.Button> свойства элемента управления <xref:System.Windows.Forms.Control.Margin%2A> и <xref:System.Windows.Forms.Control.Padding%2A> Свойства панели.

3. Измените значение <xref:System.Windows.Forms.Button> свойства элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> на <xref:System.Windows.Forms.AnchorStyles.Right> и <xref:System.Windows.Forms.AnchorStyles.Left> . Обратите внимание, что размер элемента управления изменяется по ширине ячейки с <xref:System.Windows.Forms.Control.Margin%2A> <xref:System.Windows.Forms.Control.Padding%2A> учетом значений и.

4. Повторите шаги 2 и 3 с помощью <xref:System.Windows.Forms.AnchorStyles.Top> <xref:System.Windows.Forms.AnchorStyles.Bottom> стилей и.

## <a name="setting-row-and-column-properties"></a>Установка свойств строк и столбцов

Можно задать отдельные свойства строк и столбцов с помощью <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> коллекций и.

#### <a name="to-set-row-and-column-properties"></a>Задание свойств строк и столбцов

1. Выберите <xref:System.Windows.Forms.TableLayoutPanel> элемент управления в **конструктор Windows Forms**.

2. В окнах **свойств** откройте <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> коллекцию, нажав кнопку с многоточием ( ![ ...) в окно свойств кнопки Visual Studio. ](./media/visual-studio-ellipsis-button.png) ) рядом с записью **Columns** .

3. Выберите первый столбец и измените значение его <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> Свойства на <xref:System.Windows.Forms.SizeType.AutoSize> . Чтобы принять изменение, нажмите кнопку **ОК**. Обратите внимание, что ширина первого столбца уменьшается в соответствии с <xref:System.Windows.Forms.Button> элементом управления. Также обратите внимание, что ширина столбца не может изменяться.

4. В окне **Свойства** откройте <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> коллекцию и выберите первый столбец. Измените значение его свойства <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> на <xref:System.Windows.Forms.SizeType.Percent>. Чтобы принять изменение, нажмите кнопку **ОК**. Измените размер <xref:System.Windows.Forms.TableLayoutPanel> элемента управления на более крупную ширину и обратите внимание, что ширина первого столбца расширяется. Измените размер <xref:System.Windows.Forms.TableLayoutPanel> элемента управления до меньшей ширины и обратите внимание, что кнопки в первом столбце имеют размер в соответствии с ячейкой. Также обратите внимание, что размер столбца можно изменять.

5. В окне **Свойства** откройте <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> коллекцию и выберите все перечисленные столбцы. Присвойте каждому <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> свойству значение <xref:System.Windows.Forms.SizeType.Percent> . Чтобы принять изменение, нажмите кнопку **ОК**. Повторите с помощью <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> коллекции.

6. Извлеките один из угловых маркеров изменения размера и измените ширину и высоту <xref:System.Windows.Forms.TableLayoutPanel> элемента управления. Обратите внимание, что размер строк и столбцов изменяется по мере <xref:System.Windows.Forms.TableLayoutPanel> изменения размера элемента управления. Также обратите внимание, что размер строк и столбцов можно изменять с помощью маркеров горизонтального и вертикального размера.

## <a name="spanning-rows-and-columns-with-a-control"></a>Объединение строк и столбцов с помощью элемента управления

<xref:System.Windows.Forms.TableLayoutPanel>Элемент управления добавляет несколько новых свойств в элементы управления во время разработки. Двумя из этих свойств являются `RowSpan` и `ColumnSpan` . Эти свойства можно использовать, чтобы сделать элемент управления более чем одной строкой или столбцом.

#### <a name="to-span-rows-and-columns-with-a-control"></a>Объединение строк и столбцов с помощью элемента управления

1. Выберите <xref:System.Windows.Forms.Button> элемент управления в первой строке и первом столбце.

2. В окнах **свойств** измените значение `ColumnSpan` Свойства на **2**. Обратите внимание, что <xref:System.Windows.Forms.Button> элемент управления заполняет первый столбец и второй столбец. Кроме того, обратите внимание, что для удовлетворения этого изменения была добавлена дополнительная строка.

3. Повторите шаг 2 для `RowSpan` Свойства.

## <a name="inserting-controls-by-double-clicking-them-in-the-toolbox"></a>Вставка элементов управления двойным щелчком по ним в панели элементов

Вы можете заполнять свой элемент управления <xref:System.Windows.Forms.TableLayoutPanel> , дважды щелкая элементы управления в **панели элементов**.

#### <a name="to-insert-controls-by-double-clicking-in-the-toolbox"></a>Вставка элементов управления двойным щелчком по ним в панели элементов

1. Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму.

2. Дважды щелкните значок элемента управления <xref:System.Windows.Forms.Button> в **панели элементов**. Обратите внимание, что в <xref:System.Windows.Forms.TableLayoutPanel> первой ячейке элемента управления появляется новый элемент управления "Кнопка".

3. Дважды щелкните несколько других элементов управления в **панели элементов**. Обратите внимание, что новые элементы управления последовательно появляются в <xref:System.Windows.Forms.TableLayoutPanel> незанятых ячейках элемента управления. Также обратите внимание, что <xref:System.Windows.Forms.TableLayoutPanel> элемент управления разворачивается в соответствии с новыми элементами управления, если открытые ячейки недоступны.

## <a name="automatic-handling-of-overflows"></a>Автоматическая обработка перегрузок

При вставке элементов управления в <xref:System.Windows.Forms.TableLayoutPanel> элемент управления для новых элементов управления могут закончится пустые ячейки. <xref:System.Windows.Forms.TableLayoutPanel>Элемент управления обрабатывает эту ситуацию автоматически, увеличивая число ячеек.

#### <a name="to-observe-automatic-handling-of-overflows"></a>Наблюдение за автоматической обработкой перегрузок

1. Если в элементе управления остались пустые ячейки <xref:System.Windows.Forms.TableLayoutPanel> , продолжайте вставлять новые <xref:System.Windows.Forms.Button> элементы управления, пока <xref:System.Windows.Forms.TableLayoutPanel> элемент управления не будет заполнен.

2. После <xref:System.Windows.Forms.TableLayoutPanel> заполнения элемента управления дважды щелкните <xref:System.Windows.Forms.Button> значок на **панели элементов** , чтобы вставить другой <xref:System.Windows.Forms.Button> элемент управления. Обратите внимание, что <xref:System.Windows.Forms.TableLayoutPanel> элемент управления создает новые ячейки для размещения нового элемента управления. Вставьте еще несколько элементов управления и обратите внимание на поведение изменения размера.

3. Измените значение свойства <xref:System.Windows.Forms.TableLayoutPanel> элемента управления <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> на <xref:System.Windows.Forms.TableLayoutPanelGrowStyle.FixedSize>. Дважды щелкните <xref:System.Windows.Forms.Button> значок в **области элементов** , чтобы вставить <xref:System.Windows.Forms.Button> элементы управления до <xref:System.Windows.Forms.TableLayoutPanel> заполнения элемента управления. Дважды щелкните <xref:System.Windows.Forms.Button> значок на **панели элементов** еще раз. Обратите внимание, что в **конструктор Windows Forms** появляется сообщение об ошибке, информирующее о невозможности создания дополнительных строк и столбцов.

## <a name="inserting-a-control-by-drawing-its-outline"></a>Вставка элемента управления путем рисования его контура

Вы можете вставить элемент управления в элемент управления <xref:System.Windows.Forms.TableLayoutPanel> и задать его размер, нарисовав его контур в ячейке.

#### <a name="to-insert-a-control-by-drawing-its-outline"></a>Вставка элемента управления путем рисования его контура

1. Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму.

2. В **панели элементов**щелкните значок элемента управления <xref:System.Windows.Forms.Button> . Не перетаскивайте его в форму.

3. Наведите указатель мыши на элемент управления <xref:System.Windows.Forms.TableLayoutPanel> . Обратите внимание, что указатель превратился в перекрестие с прикрепленным значком элемента управления <xref:System.Windows.Forms.Button> .

4. Нажмите и удерживайте кнопку мыши.

5. Перемещайте указатель мыши, чтобы нарисовать контур элемента управления <xref:System.Windows.Forms.Button> . Когда вас устроит размер, отпустите кнопку мыши. Обратите внимание, что <xref:System.Windows.Forms.Button> элемент управления создается в ячейке, в которой был нарисован контур элемента управления.

## <a name="multiple-controls-within-cells-are-not-permitted"></a>Использование нескольких элементов управления в ячейках не допускается

<xref:System.Windows.Forms.TableLayoutPanel>Элемент управления может содержать только один дочерний элемент управления на одну ячейку.

#### <a name="to-demonstrate-that-multiple-controls-within-cells-are-not-permitted"></a>Демонстрация того, что несколько элементов управления в ячейках не разрешены

- Перетащите <xref:System.Windows.Forms.Button> элемент управления из **панели элементов** в <xref:System.Windows.Forms.TableLayoutPanel> элемент управления и поместите его в одну из занятых ячеек. Обратите внимание, что <xref:System.Windows.Forms.TableLayoutPanel> элемент управления не позволяет поместить <xref:System.Windows.Forms.Button> элемент управления в занятую ячейку.

## <a name="swapping-controls"></a>Переключение элементов управления

<xref:System.Windows.Forms.TableLayoutPanel>Элемент управления позволяет менять местами элементы управления, занимающие две разные ячейки.

#### <a name="to-swap-controls"></a>Переключение элементов управления

- Перетащите один из <xref:System.Windows.Forms.Button> элементов управления из занятой ячейки и поместите в другую занятую ячейку. Обратите внимание, что два элемента управления перемещаются из одной ячейки в другую.

## <a name="next-steps"></a>Next Steps

Используя сочетание панелей макета и элементов управления, можно создавать сложные макеты. Для лучшего изучения можно предложить следующее:

- Попробуйте <xref:System.Windows.Forms.Button> изменить размер одного из элементов управления на больший, и обратите внимание на изменение макета.

- Вставьте в элемент управления несколько элементов управления <xref:System.Windows.Forms.TableLayoutPanel> и обратите внимание на то, как вставляются элементы управления.

- Панели макета могут содержать другие панели макета. Попробуйте вставить элемент управления <xref:System.Windows.Forms.TableLayoutPanel> в существующий элемент управления.

- Закрепите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> в родительской форме. Измените размер этой формы и обратите внимание, как это отражается на макете.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Пошаговое руководство. Создание в Windows Forms формы для ввода данных переменного размера](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))
- [Пошаговое руководство. Создание локализуемых форм Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))
- [Советы по использованию элемента управления TableLayoutPanel](best-practices-for-the-tablelayoutpanel-control.md)
- [Свойство AutoSize](autosize-property-overview.md)
- [Практическое руководство. Закрепление элементов управления в формах Windows Forms.](how-to-dock-controls-on-windows-forms.md)
- [Практическое руководство. Привязка элементов управления в формах Windows Forms](how-to-anchor-controls-on-windows-forms.md)
- [Пошаговое руководство. Создание структуры элементов управления Windows Forms с помощью свойств Padding, Margins и AutoSize](windows-forms-controls-padding-autosize.md)
