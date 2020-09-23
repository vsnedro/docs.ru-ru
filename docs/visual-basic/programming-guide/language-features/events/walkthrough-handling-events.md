---
title: Обработка событий
ms.date: 07/20/2015
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
ms.openlocfilehash: 4489f75e50a783a9b1acfb9c30568fdec6614488
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91057914"
---
# <a name="walkthrough-handling-events-visual-basic"></a>Пошаговое руководство. Обработка событий (Visual Basic)

Это второй из двух разделов, демонстрирующих работу с событиями. В первом разделе [Пошаговое руководство. объявление и создание событий](walkthrough-declaring-and-raising-events.md)показано, как объявлять и создавать события. В этом разделе используется форма и класс из этого пошагового руководства, чтобы продемонстрировать, как обрабатывались события, когда они выполняются.  
  
 В `Widget` примере класса используются традиционные инструкции по обработке событий. Visual Basic предоставляет другие методы для работы с событиями. В качестве упражнения можно изменить этот пример для использования `AddHandler` `Handles` инструкций и.  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>Для управления событием PercentDone класса Widget  
  
1. Поместите следующий код в `Form1` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#4)]  
  
     `WithEvents`Ключевое слово указывает, что переменная `mWidget` используется для управления событиями объекта. Тип объекта указывается путем указания имени класса, из которого будет создан объект.  
  
     Переменная `mWidget` объявлена в, `Form1` поскольку `WithEvents` переменные должны быть уровня класса. Это справедливо независимо от типа класса, в котором они размещены.  
  
     Переменная `mblnCancel` используется для отмены `LongTask` метода.  
  
## <a name="writing-code-to-handle-an-event"></a>Написание кода для обработчика события  

 Как только вы объявили переменную с помощью `WithEvents` , имя переменной отображается в левом раскрывающемся списке **редактора кода**класса. При выборе в `mWidget` правом раскрывающемся `Widget` списке отображаются события класса. При выборе события отображается соответствующая процедура события с префиксом `mWidget` и символом подчеркивания. Всем процедурам события, связанным с `WithEvents` переменной, присваивается имя переменной в виде префикса.  
  
#### <a name="to-handle-an-event"></a>Чтобы обработать событие  
  
1. Выберите `mWidget` из левого раскрывающегося списка в **редакторе кода**.  
  
2. Выберите `PercentDone` событие из правого раскрывающегося списка. **Редактор кода** открывает `mWidget_PercentDone` процедуру события.  
  
    > [!NOTE]
    > **Редактор кода** удобен, но не является обязательным для вставки новых обработчиков событий. В этом пошаговом руководстве более прямым просто скопировать обработчики событий непосредственно в код.  
  
3. Добавьте следующий код в обработчик событий `mWidget_PercentDone` .  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#5)]  
  
     При каждом `PercentDone` возникновении события процедура события отображает процент завершения в `Label` элементе управления. `DoEvents`Метод позволяет перекрасить метку, а также дает пользователю возможность нажать кнопку **Отмена** .  
  
4. Добавьте следующий код для `Button2_Click` обработчика событий:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#6)]  
  
 Если пользователь нажимает кнопку **Отмена** во время `LongTask` выполнения, `Button2_Click` событие выполняется сразу же после того, как `DoEvents` инструкция допускает обработку события. Переменной уровня класса присваивается `mblnCancel` значение `True` , а `mWidget_PercentDone` затем событие проверяется и присваивает `ByRef Cancel` аргументу значение `True` .  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>Подключение переменной WithEvents к объекту  

 `Form1` теперь настроен на обработку `Widget` событий объекта. Все, что остается, — найти `Widget` кое-что.  
  
 При объявлении переменной `WithEvents` во время разработки объект не связан с ним. Переменная аналогична `WithEvents` любой другой объектной переменной. Необходимо создать объект и присвоить ему ссылку на `WithEvents` переменную.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>Создание объекта и присвоение ему ссылки  
  
1. Выберите **(события Form1)** в левом раскрывающемся списке в **редакторе кода**.  
  
2. Выберите `Load` событие из правого раскрывающегося списка. **Редактор кода** открывает `Form1_Load` процедуру события.  
  
3. Добавьте следующий код для `Form1_Load` процедуры события, чтобы создать `Widget` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#7)]  
  
 При выполнении этого кода Visual Basic создает `Widget` объект и подключает его события к процедурам событий, связанным с `mWidget` . С этого момента каждый раз, когда `Widget` вызывает `PercentDone` событие, `mWidget_PercentDone` выполняется процедура события.  
  
#### <a name="to-call-the-longtask-method"></a>Вызов метода LongTask  
  
- Добавьте следующий код в обработчик событий `Button1_Click` .  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#8)]  
  
 Перед `LongTask` вызовом метода необходимо инициализировать метку, которая отображает процент завершения, а флаг уровня класса `Boolean` для отмены метода должен иметь значение `False` .  
  
 `LongTask` вызывается с длительностью задачи в 12,2 секунд. `PercentDone`Событие вызывается раз в секунду с каждой третьей стороной. При каждом возникновении события `mWidget_PercentDone` выполняется процедура события.  
  
 По `LongTask` завершении проверяется, `mblnCancel` `LongTask` завершилось ли нормальное завершение или остановлено, так как `mblnCancel` было установлено значение `True` . Процент завершения обновляется только в первом случае.  
  
#### <a name="to-run-the-program"></a>Чтобы выполнить программу, выполните следующие действия.  
  
1. Нажмите клавишу F5, чтобы перевести проект в режим выполнения.  
  
2. Нажмите кнопку **запустить задачу** . При каждом `PercentDone` возникновении события метка обновляется в процентах от завершенной задачи.  
  
3. Нажмите кнопку **Отмена** , чтобы остановить задачу. Обратите внимание, что внешний вид кнопки **Отмена** не меняется сразу же после нажатия. `Click`Событие не может произойти, пока `My.Application.DoEvents` инструкция не разрешит обработку событий.  
  
    > [!NOTE]
    > `My.Application.DoEvents`Метод не обрабатывает события точно так же, как и форма. Например, в этом пошаговом руководстве необходимо дважды нажать кнопку **Отмена** . Чтобы форма могла напрямую управлять событиями, можно использовать многопоточность. Дополнительные сведения см. в разделе [управляемые потоки](../../../../standard/threading/index.md).
  
 Может оказаться полезным запустить программу с помощью F11 и пошаговое выполнение кода. Вы можете ясно видеть, как работает выполнение `LongTask` , а затем ненадолго `Form1` перезапускать каждый раз при `PercentDone` возникновении события.  
  
 Что произойдет, если при обратном выполнении кода `Form1` `LongTask` метод был вызван повторно? В худшем случае может произойти переполнение стека, если `LongTask` вызывалось каждый раз при возникновении события.  
  
 Можно `mWidget` присвоить переменной обработку событий для другого `Widget` объекта, назначив ссылку на новый объект `Widget` в `mWidget` . На самом деле код можно сделать при `Button1_Click` каждом нажатии кнопки.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>Для управления событиями для другого мини-приложения  
  
- Добавьте следующую строку кода в `Button1_Click` процедуру, непосредственно перед строкой, которая считывает `mWidget.LongTask(12.2, 0.33)` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#9)]  
  
 Приведенный выше код создает новый при `Widget` каждом нажатии кнопки. Как только `LongTask` метод завершается, ссылка на `Widget` освобождается и `Widget` уничтожается.  
  
 `WithEvents`Переменная может содержать только одну ссылку на объект за раз, поэтому при присвоении другому объекту значения `Widget` `mWidget` `Widget` события предыдущего объекта больше не будут обрабатываться. Если `mWidget` является единственной объектной переменной, содержащей ссылку на старую `Widget` , объект уничтожается. Если требуется обрабатывать события из нескольких `Widget` объектов, используйте `AddHandler` инструкцию для обработки событий из каждого объекта отдельно.  
  
> [!NOTE]
> Можно объявить столько `WithEvents` переменных, сколько требуется, но массивы `WithEvents` переменных не поддерживаются.  
  
## <a name="see-also"></a>См. также

- [Пошаговое руководство. Объявление и вызов событий](walkthrough-declaring-and-raising-events.md)
- [События](index.md)
