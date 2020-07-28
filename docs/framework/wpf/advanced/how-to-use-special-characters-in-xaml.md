---
title: Практическое руководство. Использование специальных символов в XAML
description: Сведения о синтаксисе кодирования специальных символов в формате Юникода UTF-8 в Visual Studio для использования в файлах XAML в Windows Presentation Foundation.
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: ac2388fd96aa26ddd99408ac9f847ce517958568
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168358"
---
# <a name="how-to-use-special-characters-in-xaml"></a>Практическое руководство. Использование специальных символов в XAML
Файлы разметки, созданные в Visual Studio, автоматически сохраняются в формате Юникода UTF-8, что означает, что большинство специальных символов, таких как диакритические знаки, кодируются правильно. Но существует набор широко используемых специальных символов, которые обрабатываются по-другому. Эти специальные символы соответствуют стандарту XML для кодирования консорциум W3C (W3C).  
  
 В следующей таблице показан синтаксис кодирования этого набора специальных символов:  
  
|Символ|Синтаксис|Описание|  
|---------------|------------|-----------------|  
|<|`&lt;`|Символ "меньше чем".|  
|>|`&gt;`|Символ "больше чем".|  
|&|`&amp;`|Символ амперсанда.|  
|"|`&quot;`|Символ двойной кавычки.|  
  
> [!NOTE]
> При создании файла разметки с помощью текстового редактора, например Блокнота Windows, необходимо сохранить файл в формате Юникода UTF-8, чтобы сохранить закодированные специальные символы.  
  
 В приведенном ниже примере показано, как можно использовать специальные символы в тексте при создании разметки.  
  
## <a name="example"></a>Пример  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
