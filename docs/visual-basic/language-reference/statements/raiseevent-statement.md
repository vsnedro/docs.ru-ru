---
title: Оператор RaiseEvent
ms.date: 07/20/2015
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
ms.openlocfilehash: 46b93c060a12d82b34dafdf3aa4ea677df6f54cd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404295"
---
# <a name="raiseevent-statement"></a><span data-ttu-id="d18dd-102">Оператор RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="d18dd-102">RaiseEvent Statement</span></span>
<span data-ttu-id="d18dd-103">Запускает событие, объявленное на уровне модуля в классе, форме или документе.</span><span class="sxs-lookup"><span data-stu-id="d18dd-103">Triggers an event declared at module level within a class, form, or document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d18dd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d18dd-104">Syntax</span></span>  
  
```vb  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a><span data-ttu-id="d18dd-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="d18dd-105">Parts</span></span>  
 `eventname`  
 <span data-ttu-id="d18dd-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d18dd-106">Required.</span></span> <span data-ttu-id="d18dd-107">Имя события для активации.</span><span class="sxs-lookup"><span data-stu-id="d18dd-107">Name of the event to trigger.</span></span>  
  
 `argumentlist`  
 <span data-ttu-id="d18dd-108">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d18dd-108">Optional.</span></span> <span data-ttu-id="d18dd-109">Разделенный запятыми список переменных, массивов или выражений.</span><span class="sxs-lookup"><span data-stu-id="d18dd-109">Comma-delimited list of variables, arrays, or expressions.</span></span> <span data-ttu-id="d18dd-110">`argumentlist`Аргумент должен быть заключен в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="d18dd-110">The `argumentlist` argument must be enclosed by parentheses.</span></span> <span data-ttu-id="d18dd-111">Если аргументы отсутствуют, скобки должны быть опущены.</span><span class="sxs-lookup"><span data-stu-id="d18dd-111">If there are no arguments, the parentheses must be omitted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d18dd-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d18dd-112">Remarks</span></span>  
 <span data-ttu-id="d18dd-113">Required `eventname` — это имя события, объявленного в модуле.</span><span class="sxs-lookup"><span data-stu-id="d18dd-113">The required `eventname` is the name of an event declared within the module.</span></span> <span data-ttu-id="d18dd-114">Оно соответствует Visual Basic соглашениям об именовании переменных.</span><span class="sxs-lookup"><span data-stu-id="d18dd-114">It follows Visual Basic variable naming conventions.</span></span>  
  
 <span data-ttu-id="d18dd-115">Если событие не было объявлено в модуле, в котором оно вызывается, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="d18dd-115">If the event has not been declared within the module in which it is raised, an error occurs.</span></span> <span data-ttu-id="d18dd-116">В следующем фрагменте кода показано объявление события и процедура, в которой возникает событие.</span><span class="sxs-lookup"><span data-stu-id="d18dd-116">The following code fragment illustrates an event declaration and a procedure in which the event is raised.</span></span>  
  
 [!code-vb[VbVbalrEvents#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#37)]  
  
 <span data-ttu-id="d18dd-117">Нельзя использовать `RaiseEvent` для вызова событий, которые не объявлены явным образом в модуле.</span><span class="sxs-lookup"><span data-stu-id="d18dd-117">You cannot use `RaiseEvent` to raise events that are not explicitly declared in the module.</span></span> <span data-ttu-id="d18dd-118">Например, все формы наследуют <xref:System.Windows.Forms.Control.Click> событие от <xref:System.Windows.Forms.Form?displayProperty=nameWithType> , оно не может быть вызвано с помощью `RaiseEvent` в производной форме.</span><span class="sxs-lookup"><span data-stu-id="d18dd-118">For example, all forms inherit a <xref:System.Windows.Forms.Control.Click> event from <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, it cannot be raised using `RaiseEvent` in a derived form.</span></span> <span data-ttu-id="d18dd-119">При объявлении `Click` события в модуле формы оно скрывает собственное <xref:System.Windows.Forms.Control.Click> событие формы.</span><span class="sxs-lookup"><span data-stu-id="d18dd-119">If you declare a `Click` event in the form module, it shadows the form's own <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="d18dd-120">Событие формы по-прежнему можно вызвать <xref:System.Windows.Forms.Control.Click> , вызвав <xref:System.Windows.Forms.Control.OnClick%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="d18dd-120">You can still invoke the form's <xref:System.Windows.Forms.Control.Click> event by calling the <xref:System.Windows.Forms.Control.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="d18dd-121">По умолчанию событие, определенное в Visual Basic, вызывает обработчики событий в том порядке, в котором установлены соединения.</span><span class="sxs-lookup"><span data-stu-id="d18dd-121">By default, an event defined in Visual Basic raises its event handlers in the order that the connections are established.</span></span> <span data-ttu-id="d18dd-122">Так как события могут иметь `ByRef` Параметры, процесс, который подключается позднее, может получить параметры, которые были изменены более ранним обработчиком событий.</span><span class="sxs-lookup"><span data-stu-id="d18dd-122">Because events can have `ByRef` parameters, a process that connects late may receive parameters that have been changed by an earlier event handler.</span></span> <span data-ttu-id="d18dd-123">После выполнения обработчиков событий управление возвращается подподпрограмме, вызвавшей событие.</span><span class="sxs-lookup"><span data-stu-id="d18dd-123">After the event handlers execute, control is returned to the subroutine that raised the event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d18dd-124">Не являющиеся общими события не должны вызываться в конструкторе класса, в котором они объявляются.</span><span class="sxs-lookup"><span data-stu-id="d18dd-124">Non-shared events should not be raised within the constructor of the class in which they are declared.</span></span> <span data-ttu-id="d18dd-125">Хотя такие события не вызывают ошибок во время выполнения, они могут не перехватываться связанными обработчиками событий.</span><span class="sxs-lookup"><span data-stu-id="d18dd-125">Although such events do not cause run-time errors, they may fail to be caught by associated event handlers.</span></span> <span data-ttu-id="d18dd-126">Используйте `Shared` Модификатор для создания общего события, если необходимо вызвать событие из конструктора.</span><span class="sxs-lookup"><span data-stu-id="d18dd-126">Use the `Shared` modifier to create a shared event if you need to raise an event from a constructor.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d18dd-127">Поведение по умолчанию событий можно изменить, определив пользовательское событие.</span><span class="sxs-lookup"><span data-stu-id="d18dd-127">You can change the default behavior of events by defining a custom event.</span></span> <span data-ttu-id="d18dd-128">Для пользовательских событий `RaiseEvent` оператор вызывает `RaiseEvent` метод доступа события.</span><span class="sxs-lookup"><span data-stu-id="d18dd-128">For custom events, the `RaiseEvent` statement invokes the event's `RaiseEvent` accessor.</span></span> <span data-ttu-id="d18dd-129">Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d18dd-129">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d18dd-130">Пример</span><span class="sxs-lookup"><span data-stu-id="d18dd-130">Example</span></span>  
 <span data-ttu-id="d18dd-131">В следующем примере события используются для выполнения обратного отсчета от 10 до 0 секунд.</span><span class="sxs-lookup"><span data-stu-id="d18dd-131">The following example uses events to count down seconds from 10 to 0.</span></span> <span data-ttu-id="d18dd-132">Код иллюстрирует несколько методов, свойств и инструкций, связанных с событиями, включая `RaiseEvent` инструкцию.</span><span class="sxs-lookup"><span data-stu-id="d18dd-132">The code illustrates several of the event-related methods, properties, and statements, including the `RaiseEvent` statement.</span></span>  
  
 <span data-ttu-id="d18dd-133">Класс, который вызывает событие, является источником события, а методы, обрабатывающие события, — обработчиками событий.</span><span class="sxs-lookup"><span data-stu-id="d18dd-133">The class that raises an event is the event source, and the methods that process the event are the event handlers.</span></span> <span data-ttu-id="d18dd-134">Источник события может иметь несколько обработчиков для создаваемых им событий.</span><span class="sxs-lookup"><span data-stu-id="d18dd-134">An event source can have multiple handlers for the events it generates.</span></span> <span data-ttu-id="d18dd-135">Когда класс создает событие, это событие создается во всех классах, выбранных для обработки событий данного экземпляра объекта.</span><span class="sxs-lookup"><span data-stu-id="d18dd-135">When the class raises the event, that event is raised on every class that has elected to handle events for that instance of the object.</span></span>  
  
 <span data-ttu-id="d18dd-136">В примере также используется форма (`Form1`) с кнопкой (`Button1`) и текстовым полем (`TextBox1`).</span><span class="sxs-lookup"><span data-stu-id="d18dd-136">The example also uses a form (`Form1`) with a button (`Button1`) and a text box (`TextBox1`).</span></span> <span data-ttu-id="d18dd-137">При нажатии кнопки в первом текстовом поле отображается обратный отсчет от 10 до 0 секунд.</span><span class="sxs-lookup"><span data-stu-id="d18dd-137">When you click the button, the first text box displays a countdown from 10 to 0 seconds.</span></span> <span data-ttu-id="d18dd-138">По истечении всего времени (10 секунд) в первом текстовом поле отображается надпись Done.</span><span class="sxs-lookup"><span data-stu-id="d18dd-138">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
 <span data-ttu-id="d18dd-139">Код для `Form1` указывает начальное и конечное состояния формы.</span><span class="sxs-lookup"><span data-stu-id="d18dd-139">The code for `Form1` specifies the initial and terminal states of the form.</span></span> <span data-ttu-id="d18dd-140">Он также содержит код, выполняемый при создании событий.</span><span class="sxs-lookup"><span data-stu-id="d18dd-140">It also contains the code executed when events are raised.</span></span>  
  
 <span data-ttu-id="d18dd-141">Чтобы использовать этот пример, откройте новый проект приложения Windows, добавьте кнопку с именем `Button1` и текстовое поле с именем `TextBox1` в главную форму с именем `Form1` .</span><span class="sxs-lookup"><span data-stu-id="d18dd-141">To use this example, open a new Windows Application project, add a button named `Button1` and a text box named `TextBox1` to the main form, named `Form1`.</span></span> <span data-ttu-id="d18dd-142">Затем щелкните форму правой кнопкой мыши и выберите команду **Просмотреть код** , чтобы открыть редактор кода.</span><span class="sxs-lookup"><span data-stu-id="d18dd-142">Then right-click the form and click **View Code** to open the Code Editor.</span></span>  
  
 <span data-ttu-id="d18dd-143">Добавьте `WithEvents` переменную в раздел Declarations `Form1` класса.</span><span class="sxs-lookup"><span data-stu-id="d18dd-143">Add a `WithEvents` variable to the declarations section of the `Form1` class.</span></span>  
  
 [!code-vb[VbVbalrEvents#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="d18dd-144">Пример</span><span class="sxs-lookup"><span data-stu-id="d18dd-144">Example</span></span>  
 <span data-ttu-id="d18dd-145">Добавьте следующий код в код для `Form1`.</span><span class="sxs-lookup"><span data-stu-id="d18dd-145">Add the following code to the code for `Form1`.</span></span> <span data-ttu-id="d18dd-146">Замените все дубликаты процедур, которые могут существовать, например `Form_Load` , или `Button_Click` .</span><span class="sxs-lookup"><span data-stu-id="d18dd-146">Replace any duplicate procedures that may exist, such as `Form_Load`, or `Button_Click`.</span></span>  
  
 [!code-vb[VbVbalrEvents#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#15)]  
  
 <span data-ttu-id="d18dd-147">Нажмите клавишу F5, чтобы запустить предыдущий пример, и нажмите кнопку с надписью **Запуск**.</span><span class="sxs-lookup"><span data-stu-id="d18dd-147">Press F5 to run the preceding example, and click the button labeled **Start**.</span></span> <span data-ttu-id="d18dd-148">Первое текстовое поле начинает обратный отсчет.</span><span class="sxs-lookup"><span data-stu-id="d18dd-148">The first text box starts to count down the seconds.</span></span> <span data-ttu-id="d18dd-149">По истечении всего времени (10 секунд) в первом текстовом поле отображается надпись Done.</span><span class="sxs-lookup"><span data-stu-id="d18dd-149">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d18dd-150">`My.Application.DoEvents`Метод не обрабатывает события точно так же, как и форма.</span><span class="sxs-lookup"><span data-stu-id="d18dd-150">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="d18dd-151">Чтобы форма могла напрямую управлять событиями, можно использовать многопоточность.</span><span class="sxs-lookup"><span data-stu-id="d18dd-151">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="d18dd-152">Дополнительные сведения см. в разделе [управляемые потоки](../../../standard/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="d18dd-152">For more information, see [Managed Threading](../../../standard/threading/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d18dd-153">См. также</span><span class="sxs-lookup"><span data-stu-id="d18dd-153">See also</span></span>

- [<span data-ttu-id="d18dd-154">События</span><span class="sxs-lookup"><span data-stu-id="d18dd-154">Events</span></span>](../../programming-guide/language-features/events/index.md)
- [<span data-ttu-id="d18dd-155">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="d18dd-155">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="d18dd-156">Оператор AddHandler</span><span class="sxs-lookup"><span data-stu-id="d18dd-156">AddHandler Statement</span></span>](addhandler-statement.md)
- [<span data-ttu-id="d18dd-157">Оператор RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="d18dd-157">RemoveHandler Statement</span></span>](removehandler-statement.md)
- [<span data-ttu-id="d18dd-158">Маркеры</span><span class="sxs-lookup"><span data-stu-id="d18dd-158">Handles</span></span>](handles-clause.md)
