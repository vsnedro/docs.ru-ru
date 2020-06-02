---
title: Передача URI в среду выполнения Windows
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
ms.openlocfilehash: 7152fb02abf430c0d0e27b82550e4006e3958e93
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288892"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a>Передача URI в среду выполнения Windows
Методы среды выполнения Windows принимают только абсолютные URI. Если передать относительный URI в метод среда выполнения Windows, <xref:System.ArgumentException> создается исключение. Вот почему: при использовании среда выполнения Windows в .NET Frameworkном коде <xref:Windows.Foundation.Uri?displayProperty=nameWithType> класс отображается как <xref:System.Uri?displayProperty=nameWithType> IntelliSense. <xref:System.Uri?displayProperty=nameWithType>Класс допускает относительные URI, но <xref:Windows.Foundation.Uri?displayProperty=nameWithType> не класс. Это также справедливо для методов, предоставляемых в среда выполнения Windowsных компонентах. Если компонент предоставляет метод, принимающий URI, сигнатура в коде содержит <xref:System.Uri?displayProperty=nameWithType>. Однако для пользователей компонента подпись включает <xref:Windows.Foundation.Uri?displayProperty=nameWithType> . URI, переданный вашему компоненту, должен быть абсолютным.  
  
В этом разделе показано, как определить абсолютный URI и как создать его при указании ссылки на ресурс в пакете приложения.  
  
## <a name="detecting-and-using-an-absolute-uri"></a>Определение и использование абсолютного URI  
Используйте <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> свойство, чтобы убедиться, что URI является абсолютным, прежде чем передать его в среда выполнения Windows. Такой подход более эффективен, чем перехват и обработка исключения <xref:System.ArgumentException>.  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a>Использование абсолютного URI для ресурса в пакете приложения  
Чтобы указать URI для ресурса в пакете приложения, можно использовать схему `ms-appx` или `ms-appx-web` для создания абсолютного URI.  
  
В следующем примере показано, как установить <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> свойство для <xref:Windows.UI.Xaml.Controls.WebView> элемента управления и <xref:Windows.UI.Xaml.Controls.Image.Source%2A> свойство для <xref:Windows.UI.Xaml.Controls.Image> элемента управления на ресурсы, содержащиеся в папке с именем Pages, с использованием XAML и кода.  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
Дополнительные сведения об этих схемах см. в статье [Схемы URI](/windows/uwp/app-resources/uri-schemes) в Центре разработки для Windows.  
  
## <a name="see-also"></a>См. также

- [Поддержка приложений для Магазина Windows и среды выполнения Windows в .NET Framework](support-for-windows-store-apps-and-windows-runtime.md)
