---
title: Практическое руководство. Прием событий в приложениях Web Forms
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- events [.NET Framework], Web Forms
- Web Forms controls, and events
- event handlers [.NET Framework], Web Forms
- events [.NET Framework], consuming
- Web Forms, event handling
ms.assetid: 73bf8638-c4ec-4069-b0bb-a1dc79b92e32
ms.openlocfilehash: 3490b6fb89bfe6d7ac778078f58381bb5172e2fe
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288489"
---
# <a name="how-to-consume-events-in-a-web-forms-application"></a>Практическое руководство. Прием событий в приложениях Web Forms
Распространенный сценарий в приложениях веб-форм ASP.NET — заполнение веб-страницы элементами управления и выполнение определенных действий в зависимости от того, какой элемент управления выбрал пользователь. Например, элемент управления <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> вызывает событие, когда пользователь щелкает его на странице. При обработке события приложение может выполнить соответствующую логику приложения для этого нажатия кнопки.  
  
### <a name="to-handle-a-button-click-event-on-a-webpage"></a>Обработка события нажатия кнопки на веб-странице  
  
1. Создайте страницу веб-форм ASP.NET, содержащую элемент управления <xref:System.Web.UI.WebControls.Button>, значение `OnClick` которого равно имени метода, который будет определен на следующем шаге.  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2. Определите обработчик событий, который соответствует сигнатуре делегата события <xref:System.Web.UI.WebControls.Button.Click>, с именем, определенным для значения `OnClick`.  
  
    ```csharp  
    protected void Button1_Click(object sender, EventArgs e)  
    {  
        // perform action  
    }  
    ```  
  
    ```vb  
    Protected Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
        ' perform action  
    End Sub  
    ```  
  
     Событие <xref:System.Web.UI.WebControls.Button.Click> использует класс <xref:System.EventHandler> для типа делегата и класс <xref:System.EventArgs> для данных события. Платформа, на которой работает страница ASP.NET, автоматически формирует код, создающий экземпляр <xref:System.EventHandler>, и добавляет этот экземпляр делегата в событие <xref:System.Web.UI.WebControls.Button.Click> экземпляра <xref:System.Web.UI.WebControls.Button>.  
  
3. В метод обработчика событий, определенный на втором шаге, добавьте код для выполнения действий, которые должны быть выполнены при возникновении события.  
  
## <a name="see-also"></a>См. также раздел

- [События](index.md)
