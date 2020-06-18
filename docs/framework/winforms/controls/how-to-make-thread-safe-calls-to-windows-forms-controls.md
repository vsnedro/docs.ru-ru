---
title: Осуществление потокобезопасных вызовов элементов управления
ms.date: 02/19/2019
description: Узнайте, как реализовать многопоточность в приложении путем вызова элементов управления между потоками потокобезопасным способом.
dev_langs:
- csharp
- vb
f1_keywords:
- EHInvalidOperation.WinForms.IllegalCrossThreadCall
helpviewer_keywords:
- thread safety [Windows Forms], calling controls [Windows Forms]
- calling controls [Windows Forms], thread safety [Windows Forms]
- CheckForIllegalCrossThreadCalls property [Windows Forms]
- Windows Forms controls [Windows Forms], multithreading
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], cross-thread calls
- controls [Windows Forms], multithreading
ms.assetid: 138f38b6-1099-4fd5-910c-390b41cbad35
ms.openlocfilehash: b5f4de7bd3d8d89de98dbe27e2dbf360763670d0
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904186"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a>Пошаговое руководство. Осуществление потокобезопасных вызовов элементов управления Windows Forms

Многопоточность может повысить производительность Windows Forms приложений, но доступ к элементам управления Windows Forms не является потокобезопасным. Многопоточность может представлять код для очень серьезных и сложных ошибок. Два или более потока, управляющих элементом управления, могут привести к нестабильному состоянию и вызвать условия гонки, взаимоблокировки, зависания или фиксации. При реализации многопоточности в приложении следует обязательно вызывать элементы управления между потоками потокобезопасным образом. Дополнительные сведения см. в разделе рекомендации по [управляемому потоку](../../../standard/threading/managed-threading-best-practices.md).

Существует два способа безопасного вызова элемента управления Windows Forms из потока, который не был создан этим элементом управления. Метод можно использовать <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> для вызова делегата, созданного в основном потоке, который, в свою очередь, вызывает элемент управления. Или можно реализовать <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> , который использует модель, управляемую событиями, для разделения работы, выполненной в фоновом потоке, от создания отчетов о результатах.

## <a name="unsafe-cross-thread-calls"></a>Ненадежные вызовы между потоками

Вызвать элемент управления напрямую из потока, который не создал его, неважно. В следующем фрагменте кода показан незащищенный вызов <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> элемента управления. `Button1_Click`Обработчик событий создает новый `WriteTextUnsafe` поток, который устанавливает свойство основного потока <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> напрямую.

```csharp
private void Button1_Click(object sender, EventArgs e)
{
    thread2 = new Thread(new ThreadStart(WriteTextUnsafe));
    thread2.Start();
}
private void WriteTextUnsafe()
{
    textBox1.Text = "This text was set unsafely.";
}
```

```vb
Private Sub Button1_Click(ByVal sender As Object, e As EventArgs) Handles Button1.Click
    Thread2 = New Thread(New ThreadStart(AddressOf WriteTextUnsafe))
    Thread2.Start()
End Sub

Private Sub WriteTextUnsafe()
    TextBox1.Text = "This text was set unsafely."
End Sub
```

Отладчик Visual Studio обнаруживает эти ненадежные вызовы потоков путем вызова исключения <xref:System.InvalidOperationException> с сообщением, **недопустимой операцией между потоками. Доступ к элементу управления "" осуществляется из потока, отличного от потока, в котором он был создан.** <xref:System.InvalidOperationException>Всегда происходит для ненадежных межпотоковых вызовов во время отладки Visual Studio и может возникнуть во время выполнения приложения. Проблему следует устранить, но можно отключить исключение, задав <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> для свойства значение `false` .

## <a name="safe-cross-thread-calls"></a>Надежные вызовы между потоками

В следующих примерах кода демонстрируются два способа безопасного вызова элемента управления Windows Forms из потока, который не создал его.

1. <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName>Метод, который вызывает делегат из основного потока для вызова элемента управления.
2. <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>Компонент, который предоставляет модель, управляемую событиями.

В обоих примерах фоновый поток заждет одну секунду для имитации работы, выполняемой в этом потоке.

Вы можете собрать и запустить эти примеры как .NET Framework приложения из командной строки C# или Visual Basic. Дополнительные сведения см. в разделе [Построение из командной строки с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) или [Сборка из командной строки (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).

Начиная с .NET Core 3,0, можно также создавать и запускать примеры как приложения Windows .NET Core из папки с файлом проекта .NET Core Windows Forms * \<folder name> . csproj* .

## <a name="example-use-the-invoke-method-with-a-delegate"></a>Пример. использование метода Invoke с делегатом

В следующем примере показан шаблон для обеспечения потокобезопасных вызовов элемента управления Windows Forms. Он запрашивает <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> свойство, которое СРАВНИВАЕТ идентификатор потока создаваемого элемента управления с идентификатором вызывающего потока. Если идентификаторы потоков совпадают, он вызывает элемент управления напрямую. Если идентификаторы потоков отличаются, он вызывает <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> метод с делегатом из основного потока, который выполняет фактический вызов элемента управления.

`SafeCallDelegate`Позволяет задать <xref:System.Windows.Forms.TextBox> свойство элемента управления <xref:System.Windows.Forms.TextBox.Text%2A> . `WriteTextSafe`Метод запрашивает <xref:System.Windows.Forms.Control.InvokeRequired%2A> . Если <xref:System.Windows.Forms.Control.InvokeRequired%2A> возвращает `true` , `WriteTextSafe` передает в `SafeCallDelegate` метод, <xref:System.Windows.Forms.Control.Invoke%2A> чтобы выполнить фактический вызов элемента управления. Если <xref:System.Windows.Forms.Control.InvokeRequired%2A> возвращает `false` , `WriteTextSafe` задает <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> непосредственно. `Button1_Click`Обработчик событий создает новый поток и выполняет `WriteTextSafe` метод.

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a>Пример. использование обработчика событий BackgroundWorker

Простой способ реализации многопоточности заключается в использовании <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> компонента, использующего модель, управляемую событиями. Фоновый поток запускает <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> событие, которое не взаимодействует с основным потоком. Главный поток запускает <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> обработчики событий и, которые могут вызывать элементы управления основного потока.

Чтобы сделать потокобезопасный вызов с помощью <xref:System.ComponentModel.BackgroundWorker> , создайте метод в фоновом потоке, чтобы выполнить работу, и привяжите его к <xref:System.ComponentModel.BackgroundWorker.DoWork> событию. Создайте другой метод в основном потоке, чтобы сообщить результаты фоновой работы и привязать его к <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> событию или. Чтобы запустить фоновый поток, вызовите <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType> .

В примере с помощью <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> обработчика событий задается <xref:System.Windows.Forms.TextBox> свойство элемента управления <xref:System.Windows.Forms.TextBox.Text%2A> . Пример использования <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> события см. в разделе <xref:System.ComponentModel.BackgroundWorker> .

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a>См. также раздел

- <xref:System.ComponentModel.BackgroundWorker>
- [Как выполнить операцию в фоновом режиме](how-to-run-an-operation-in-the-background.md)
- [Как реализовать форму, использующую фоновую операцию](how-to-implement-a-form-that-uses-a-background-operation.md)
- [Разработка пользовательских элементов управления Windows Forms с помощью .NET Framework](developing-custom-windows-forms-controls.md)
