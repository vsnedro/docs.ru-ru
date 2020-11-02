---
title: Проверка строк на соответствие формату электронной почты
description: Вы можете ознакомиться с примером того, как регулярное выражение проверяет строки на соответствие формату электронной почты в .NET.
ms.date: 06/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, examples
- user input, examples
- Regex.IsMatch method
- regular expressions [.NET], examples
- examples [Visual Basic], strings
- IsValidEmail
- validation, email strings
- input, checking
- strings [.NET], examples [Visual Basic]
- email [.NET], validating
- IsMatch method
ms.assetid: 7536af08-4e86-4953-98a1-a8298623df92
ms.openlocfilehash: 07b8e31e4a0203b87492eb01ab686a1c56f5565d
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889079"
---
# <a name="how-to-verify-that-strings-are-in-valid-email-format"></a><span data-ttu-id="c4ce2-103">Проверка строк на соответствие формату электронной почты</span><span class="sxs-lookup"><span data-stu-id="c4ce2-103">How to verify that strings are in valid email format</span></span>

<span data-ttu-id="c4ce2-104">В следующем примере регулярное выражение используется, чтобы проверить, имеет ли строка допустимый формат адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-104">The following example uses a regular expression to verify that a string is in valid email format.</span></span>

<span data-ttu-id="c4ce2-105">Это регулярное выражение довольно простое по сравнению с тем, которое может применяться в качестве сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-105">This regular expression is comparatively simple to what can actually be used as an email.</span></span> <span data-ttu-id="c4ce2-106">Использование регулярного выражения для проверки сообщения электронной почты полезно для того, чтобы убедиться в правильности структуры сообщения, но оно не заменяет собой проверку факта существования сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-106">Using a regular expression to validate an email is useful to make sure the structure of an email is correct, but it isn't a substitution for verifying the email actually exists.</span></span>

<span data-ttu-id="c4ce2-107">✔️ Используйте небольшое регулярное выражение для проверки действительной структуры сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-107">✔️ DO use a small regular expression to check for the valid structure of an email.</span></span>

<span data-ttu-id="c4ce2-108">✔️ Отправьте тестовое сообщение по адресу, предоставленному пользователем приложения.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-108">✔️ DO send a test email to the address provided by a user of your app.</span></span>

<span data-ttu-id="c4ce2-109">❌ НЕ используйте регулярное выражение в качестве единственного способа проверки сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-109">❌ DON'T use a regular expression as the only way you validate an email.</span></span>

<span data-ttu-id="c4ce2-110">Если вы попытаетесь создать _идеальное_ регулярное выражение для проверки правильности структуры сообщения, выражение становится настолько сложным, что его практически невозможно отладить или улучшить.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-110">If you try to create the _perfect_ regular expression to validate that the structure of an email is correct, the expression becomes so complex that it's incredibly difficult to debug or improve.</span></span> <span data-ttu-id="c4ce2-111">Регулярные выражения не могут проверить существование сообщения электронной почты, даже если оно структурировано правильно.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-111">Regular expressions can't validate an email exists, even if it's structured correctly.</span></span> <span data-ttu-id="c4ce2-112">Лучшим способом проверки сообщения электронной почты является отправка тестового сообщения электронной почты по адресу.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-112">The best way to validate an email is to send a test email to the address.</span></span>

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a><span data-ttu-id="c4ce2-113">Пример</span><span class="sxs-lookup"><span data-stu-id="c4ce2-113">Example</span></span>

<span data-ttu-id="c4ce2-114">В примере определяется метод `IsValidEmail`, который возвращает значение `true`, если строка содержит допустимый адрес электронной почты, и значение `false`, если она его не содержит, но не выполняет никаких других действий.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-114">The example defines an `IsValidEmail` method, which returns `true` if the string contains a valid email address and `false` if it doesn't, but takes no other action.</span></span>

<span data-ttu-id="c4ce2-115">Чтобы проверить, что адрес электронной почты допустим, метод `IsValidEmail` вызывает метод <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> с шаблоном регулярного выражения `(@)(.+)$` для выделения доменного имени из адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-115">To verify that the email address is valid, the `IsValidEmail` method calls the <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> method with the `(@)(.+)$` regular expression pattern to separate the domain name from the email address.</span></span> <span data-ttu-id="c4ce2-116">Третий параметр — это делегат <xref:System.Text.RegularExpressions.MatchEvaluator> , представляющий метод, который обрабатывает и заменяет найденный текст.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-116">The third parameter is a <xref:System.Text.RegularExpressions.MatchEvaluator> delegate that represents the method that processes and replaces the matched text.</span></span> <span data-ttu-id="c4ce2-117">Шаблон регулярного выражения интерпретируется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-117">The regular expression pattern is interpreted as follows.</span></span>

| <span data-ttu-id="c4ce2-118">Шаблон</span><span class="sxs-lookup"><span data-stu-id="c4ce2-118">Pattern</span></span> | <span data-ttu-id="c4ce2-119">Описание</span><span class="sxs-lookup"><span data-stu-id="c4ce2-119">Description</span></span>                                                                         |
|---------|-------------------------------------------------------------------------------------|
| `(@)`   | <span data-ttu-id="c4ce2-120">Совпадение с символом @.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-120">Match the @ character.</span></span> <span data-ttu-id="c4ce2-121">Это часть первой группы записи.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-121">This part is the first capturing group.</span></span>                           |
| `(.+)`  | <span data-ttu-id="c4ce2-122">Совпадение с одним или несколькими вхождениями любого символа.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-122">Match one or more occurrences of any character.</span></span> <span data-ttu-id="c4ce2-123">Это часть второй группы записи.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-123">This part is the second capturing group.</span></span> |
| `$`     | <span data-ttu-id="c4ce2-124">Совпадение должно заканчиваться в конце строки.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-124">End the match at the end of the string.</span></span>                                             |

<span data-ttu-id="c4ce2-125">Доменное имя вместе с символом @ передается методу `DomainMapper` , который использует класс <xref:System.Globalization.IdnMapping> для преобразования символов Юникода, находящихся вне диапазона символов US-ASCII, в формат Punycode.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-125">The domain name along with the @ character is passed to the `DomainMapper` method, which uses the <xref:System.Globalization.IdnMapping> class to translate Unicode characters that are outside the US-ASCII character range to Punycode.</span></span> <span data-ttu-id="c4ce2-126">Метод также устанавливает флаг `invalid` в значение `True`, если метод <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType> находит какие-либо недопустимые символы в доменном имени.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-126">The method also sets the `invalid` flag to `True` if the <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType> method detects any invalid characters in the domain name.</span></span> <span data-ttu-id="c4ce2-127">Метод возвращает доменное имя в формате Punycode, которому предшествует символ @, методу `IsValidEmail` .</span><span class="sxs-lookup"><span data-stu-id="c4ce2-127">The method returns the Punycode domain name preceded by the @ symbol to the `IsValidEmail` method.</span></span>

> [!TIP]
> <span data-ttu-id="c4ce2-128">Рекомендуется использовать простой шаблон регулярного выражения `(@)(.+)$` для нормализации домена, а затем возвратить значение, указывающее, что проверка завершилась успешно или сбоем.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-128">It's recommended that you use use the simple `(@)(.+)$` regular expression pattern to normalize the domain and then return a value indicating that it passed or failed.</span></span> <span data-ttu-id="c4ce2-129">Однако в примере в этой статье описывается дальнейшее использование регулярного выражения для проверки сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-129">However, the example in this article describes how to further use a regular expression to validate the email.</span></span> <span data-ttu-id="c4ce2-130">Независимо от способа проверки сообщения электронной почты, необходимо всегда отправлять тестовое сообщение по адресу, чтобы убедиться, что он существует.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-130">Regardless of how you validate an email, you should always send a test email to the address to make sure it exists.</span></span>

<span data-ttu-id="c4ce2-131">Метод `IsValidEmail` затем вызывает метод <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType>, чтобы убедиться, что адрес соответствует шаблону регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-131">The `IsValidEmail` method then calls the <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType> method to verify that the address conforms to a regular expression pattern.</span></span>

<span data-ttu-id="c4ce2-132">Метод `IsValidEmail` просто определяет, допустим ли формат электронной почты для адреса электронной почты; он не проверяет существование сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-132">The `IsValidEmail` method merely determines whether the email format is valid for an email address, it doesn't validate that the email exists.</span></span> <span data-ttu-id="c4ce2-133">Кроме того, метод `IsValidEmail` не проверяет, является ли доменное имя верхнего уровня действительным доменным именем, присутствующим в [базе данных корневых зон IANA](https://www.iana.org/domains/root/db), что потребовало бы операции поиска.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-133">Also, the `IsValidEmail` method doesn't verify that the top-level domain name is a valid domain name listed at the [IANA Root Zone Database](https://www.iana.org/domains/root/db), which would require a look-up operation.</span></span>

:::code language="csharp" source="snippets/how-to-verify-that-strings-are-in-valid-email-format/csharp/RegexUtilities.cs":::

:::code language="vb" source="snippets/how-to-verify-that-strings-are-in-valid-email-format/vb/RegexUtilities.vb":::

<span data-ttu-id="c4ce2-134">Возможные интерпретации шаблона регулярного выражения `^[^@\s]+@[^@\s]+\.[^@\s]+$` в этом примере показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-134">In this example, the regular expression pattern `^[^@\s]+@[^@\s]+\.[^@\s]+$` is interpreted as shown in the following table.</span></span> <span data-ttu-id="c4ce2-135">Регулярное выражение компилируется с флагом <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-135">The regular expression is compiled using the <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> flag.</span></span>

| <span data-ttu-id="c4ce2-136">Шаблон</span><span class="sxs-lookup"><span data-stu-id="c4ce2-136">Pattern</span></span>   | <span data-ttu-id="c4ce2-137">Описание</span><span class="sxs-lookup"><span data-stu-id="c4ce2-137">Description</span></span>                                                                              |
|-----------|------------------------------------------------------------------------------------------|
| `^`       | <span data-ttu-id="c4ce2-138">Соответствие должно обнаруживаться в начале строки.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-138">Begin the match at the start of the string.</span></span>                                              |
| `[^@\s]+` | <span data-ttu-id="c4ce2-139">Совпадение с одним или несколькими вхождениями любого символа, кроме символа @ или пробела.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-139">Match one or more occurrences of any character other than the @ character or whitespace.</span></span> |
| `@`       | <span data-ttu-id="c4ce2-140">Совпадение с символом @.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-140">Match the @ character.</span></span>                                                                   |
| `[^@\s]+` | <span data-ttu-id="c4ce2-141">Совпадение с одним или несколькими вхождениями любого символа, кроме символа @ или пробела.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-141">Match one or more occurrences of any character other than the @ character or whitespace.</span></span> |
| `\.`      | <span data-ttu-id="c4ce2-142">Совпадение с символом точки.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-142">Match a single period character.</span></span>                                                         |
| `[^@\s]+` | <span data-ttu-id="c4ce2-143">Совпадение с одним или несколькими вхождениями любого символа, кроме символа @ или пробела.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-143">Match one or more occurrences of any character other than the @ character or whitespace.</span></span> |
| `$`       | <span data-ttu-id="c4ce2-144">Совпадение должно заканчиваться в конце строки.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-144">End the match at the end of the string.</span></span>                                                  |

> [!IMPORTANT]
> <span data-ttu-id="c4ce2-145">Это регулярное выражение не предназначено для проверки каждого аспекта допустимого адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-145">This regular expression is not intended to cover every aspect of a valid email address.</span></span> <span data-ttu-id="c4ce2-146">Он предоставляется в качестве примера для расширения по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="c4ce2-146">It's provided as an example for you to extend as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4ce2-147">См. также</span><span class="sxs-lookup"><span data-stu-id="c4ce2-147">See also</span></span>

- [<span data-ttu-id="c4ce2-148">Регулярные выражения .NET</span><span class="sxs-lookup"><span data-stu-id="c4ce2-148">.NET Regular Expressions</span></span>](regular-expressions.md)
- [<span data-ttu-id="c4ce2-149">Насколько тщательно следует проверять адрес электронной почты?</span><span class="sxs-lookup"><span data-stu-id="c4ce2-149">How far should one take e-mail address validation?</span></span>](https://softwareengineering.stackexchange.com/questions/78353/how-far-should-one-take-e-mail-address-validation#78363)
