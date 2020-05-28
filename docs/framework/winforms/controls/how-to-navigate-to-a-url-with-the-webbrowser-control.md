---
title: Практическое руководство. Переход по заданному URL с помощью элемента управления WebBrowser
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
ms.openlocfilehash: f6cb26ff247bba75cc351d453314bade2d38d9f5
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144842"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="6246e-102">Практическое руководство. Переход по заданному URL с помощью элемента управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="6246e-102">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="6246e-103">В следующем примере кода показано, как перемещаться по <xref:System.Windows.Forms.WebBrowser> элементу управления по определенному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="6246e-103">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>

 <span data-ttu-id="6246e-104">Чтобы определить, когда новый документ полностью загружен, обработайте <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> событие.</span><span class="sxs-lookup"><span data-stu-id="6246e-104">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="6246e-105">Демонстрацию этого события см. в разделе [практические руководства. печать с помощью элемента управления WebBrowser](how-to-print-with-a-webbrowser-control.md).</span><span class="sxs-lookup"><span data-stu-id="6246e-105">For a demonstration of this event, see [How to: Print with a WebBrowser Control](how-to-print-with-a-webbrowser-control.md).</span></span>

## <a name="example"></a><span data-ttu-id="6246e-106">Пример</span><span class="sxs-lookup"><span data-stu-id="6246e-106">Example</span></span>

```vb
Me.webBrowser1.Navigate("https://www.microsoft.com")
```

```csharp
this.webBrowser1.Navigate("https://www.microsoft.com");
```

## <a name="compiling-the-code"></a><span data-ttu-id="6246e-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="6246e-107">Compiling the Code</span></span>
 <span data-ttu-id="6246e-108">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="6246e-108">This example requires:</span></span>

- <span data-ttu-id="6246e-109">элемент управления <xref:System.Windows.Forms.WebBrowser> с именем `webBrowser1`;</span><span class="sxs-lookup"><span data-stu-id="6246e-109">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>

- <span data-ttu-id="6246e-110">ссылки на сборки `System` и `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="6246e-110">References to the `System` and `System.Windows.Forms` assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="6246e-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6246e-111">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [<span data-ttu-id="6246e-112">Элемент управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="6246e-112">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
- [<span data-ttu-id="6246e-113">Практическое руководство. Печать с использованием элемента управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="6246e-113">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
