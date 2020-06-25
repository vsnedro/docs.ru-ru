---
title: Практическое руководство. Переход по заданному URL с помощью элемента управления WebBrowser
description: Узнайте, как использовать Windows Forms WebBrowser. Navigate для перехода по определенному URL-адресу. Также Узнайте, как определить, когда загружается новый документ.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.Navigate
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- URLs [Windows Forms], navigating to
- WebBrowser control [Windows Forms], navigating to URLs
- examples [Windows Forms], WebBrowser control
ms.assetid: b3ec38cb-f509-4d0b-bd79-9f3611259c62
ms.openlocfilehash: e6ad360cc73a84ca040869832bb59d354cb78bd5
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325565"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="c7b90-104">Практическое руководство. Переход по заданному URL с помощью элемента управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="c7b90-104">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="c7b90-105">В следующем примере кода показано, как перемещаться по <xref:System.Windows.Forms.WebBrowser> элементу управления по определенному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="c7b90-105">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>

 <span data-ttu-id="c7b90-106">Чтобы определить, когда новый документ полностью загружен, обработайте <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> событие.</span><span class="sxs-lookup"><span data-stu-id="c7b90-106">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="c7b90-107">Демонстрацию этого события см. в разделе [практические руководства. печать с помощью элемента управления WebBrowser](how-to-print-with-a-webbrowser-control.md).</span><span class="sxs-lookup"><span data-stu-id="c7b90-107">For a demonstration of this event, see [How to: Print with a WebBrowser Control](how-to-print-with-a-webbrowser-control.md).</span></span>

## <a name="example"></a><span data-ttu-id="c7b90-108">Пример</span><span class="sxs-lookup"><span data-stu-id="c7b90-108">Example</span></span>

```vb
Me.webBrowser1.Navigate("https://www.microsoft.com")
```

```csharp
this.webBrowser1.Navigate("https://www.microsoft.com");
```

## <a name="compiling-the-code"></a><span data-ttu-id="c7b90-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="c7b90-109">Compiling the Code</span></span>
 <span data-ttu-id="c7b90-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="c7b90-110">This example requires:</span></span>

- <span data-ttu-id="c7b90-111">элемент управления <xref:System.Windows.Forms.WebBrowser> с именем `webBrowser1`;</span><span class="sxs-lookup"><span data-stu-id="c7b90-111">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>

- <span data-ttu-id="c7b90-112">ссылки на сборки `System` и `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="c7b90-112">References to the `System` and `System.Windows.Forms` assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7b90-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c7b90-113">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [<span data-ttu-id="c7b90-114">Элемент управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="c7b90-114">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
- [<span data-ttu-id="c7b90-115">Практическое руководство. Печать с использованием элемента управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="c7b90-115">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
