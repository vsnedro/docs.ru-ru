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
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="1bec9-103">Практическое руководство. Использование специальных символов в XAML</span><span class="sxs-lookup"><span data-stu-id="1bec9-103">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="1bec9-104">Файлы разметки, созданные в Visual Studio, автоматически сохраняются в формате Юникода UTF-8, что означает, что большинство специальных символов, таких как диакритические знаки, кодируются правильно.</span><span class="sxs-lookup"><span data-stu-id="1bec9-104">Markup files that are created in Visual Studio are automatically saved in the Unicode UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="1bec9-105">Но существует набор широко используемых специальных символов, которые обрабатываются по-другому.</span><span class="sxs-lookup"><span data-stu-id="1bec9-105">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="1bec9-106">Эти специальные символы соответствуют стандарту XML для кодирования консорциум W3C (W3C).</span><span class="sxs-lookup"><span data-stu-id="1bec9-106">These special characters follow the World Wide Web Consortium (W3C) XML standard for encoding.</span></span>  
  
 <span data-ttu-id="1bec9-107">В следующей таблице показан синтаксис кодирования этого набора специальных символов:</span><span class="sxs-lookup"><span data-stu-id="1bec9-107">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="1bec9-108">Символ</span><span class="sxs-lookup"><span data-stu-id="1bec9-108">Character</span></span>|<span data-ttu-id="1bec9-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1bec9-109">Syntax</span></span>|<span data-ttu-id="1bec9-110">Описание</span><span class="sxs-lookup"><span data-stu-id="1bec9-110">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="1bec9-111">Символ "меньше чем".</span><span class="sxs-lookup"><span data-stu-id="1bec9-111">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="1bec9-112">Символ "больше чем".</span><span class="sxs-lookup"><span data-stu-id="1bec9-112">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="1bec9-113">Символ амперсанда.</span><span class="sxs-lookup"><span data-stu-id="1bec9-113">Ampersand symbol.</span></span>|  
|<span data-ttu-id="1bec9-114">"</span><span class="sxs-lookup"><span data-stu-id="1bec9-114">"</span></span>|`&quot;`|<span data-ttu-id="1bec9-115">Символ двойной кавычки.</span><span class="sxs-lookup"><span data-stu-id="1bec9-115">Double quote symbol.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="1bec9-116">При создании файла разметки с помощью текстового редактора, например Блокнота Windows, необходимо сохранить файл в формате Юникода UTF-8, чтобы сохранить закодированные специальные символы.</span><span class="sxs-lookup"><span data-stu-id="1bec9-116">If you create a markup file using a text editor, such as Windows Notepad, you must save the file in the Unicode UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="1bec9-117">В приведенном ниже примере показано, как можно использовать специальные символы в тексте при создании разметки.</span><span class="sxs-lookup"><span data-stu-id="1bec9-117">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bec9-118">Пример</span><span class="sxs-lookup"><span data-stu-id="1bec9-118">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
