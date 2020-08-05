---
title: Безопасность и ввод данных пользователем
description: Код может передавать пользовательские данные в качестве параметров в другой код, что может повлиять на безопасность. Можно выполнить проверку диапазона, чтобы отклонить проблемные входные данные.
ms.date: 07/15/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET], user input
- user input, security
- secure coding, user input
- code security, user input
ms.assetid: 9141076a-96c9-4b01-93de-366bb1d858bc
ms.openlocfilehash: e46bf8e653567637b4e6236849981fdb32df447c
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555946"
---
# <a name="security-and-user-input"></a><span data-ttu-id="96bad-104">Безопасность и ввод данных пользователем</span><span class="sxs-lookup"><span data-stu-id="96bad-104">Security and User Input</span></span>

<span data-ttu-id="96bad-105">Пользовательские данные, представляющие собой любой вид входных данных (данные из веб-запроса или URL-адрес, входные данные в элементы управления приложения Microsoft Windows Forms и так далее), могут отрицательно влиять на код, поскольку такие данные часто используются непосредственно как параметры для вызова другого кода.</span><span class="sxs-lookup"><span data-stu-id="96bad-105">User data, which is any kind of input (data from a Web request or URL, input to controls of a Microsoft Windows Forms application, and so on), can adversely influence code because often that data is used directly as parameters to call other code.</span></span> <span data-ttu-id="96bad-106">Такое поведение аналогично поведению вредоносного кода, вызывающего ваш код со странными параметрами, поэтому следует предпринимать такие же меры предосторожности.</span><span class="sxs-lookup"><span data-stu-id="96bad-106">This situation is analogous to malicious code calling your code with strange parameters, and the same precautions should be taken.</span></span> <span data-ttu-id="96bad-107">Ввод данных пользователем на самом деле защитить несколько труднее, поскольку нет кадра стека, с помощью которого можно отслеживать наличие потенциально недоверенных данных.</span><span class="sxs-lookup"><span data-stu-id="96bad-107">User input is actually harder to make safe because there is no stack frame to trace the presence of the potentially untrusted data.</span></span>

<span data-ttu-id="96bad-108">Это одна из ошибок безопасности, которые наиболее сложно найти, поскольку несмотря на то, что они находятся в коде, на первый взгляд не связанном с безопасностью, такие данные играют роль шлюза для передачи неверных данных в другой код.</span><span class="sxs-lookup"><span data-stu-id="96bad-108">These are among the subtlest and hardest security bugs to find because, although they can exist in code that is seemingly unrelated to security, they are a gateway to pass bad data through to other code.</span></span> <span data-ttu-id="96bad-109">В процессе поиска подобных ошибок проанализируйте все входные данные, все возможные диапазоны значений и определите, может ли код в случае обнаружения таких данных корректно их обработать.</span><span class="sxs-lookup"><span data-stu-id="96bad-109">To look for these bugs, follow any kind of input data, imagine what the range of possible values might be, and consider whether the code seeing this data can handle all those cases.</span></span> <span data-ttu-id="96bad-110">Такие ошибки можно устранить посредством проверки диапазонов и отбрасывания любых входных данных, которые не могут быть обработаны кодом.</span><span class="sxs-lookup"><span data-stu-id="96bad-110">You can fix these bugs through range checking and rejecting any input the code cannot handle.</span></span>

<span data-ttu-id="96bad-111">Ниже приведены некоторые важные аспекты, связанные с данными пользователя.</span><span class="sxs-lookup"><span data-stu-id="96bad-111">Some important considerations involving user data include the following:</span></span>

- <span data-ttu-id="96bad-112">Все данные пользователя в ответе сервера выполняются в контексте узла сервера на клиенте.</span><span class="sxs-lookup"><span data-stu-id="96bad-112">Any user data in a server response runs in the context of the server's site on the client.</span></span> <span data-ttu-id="96bad-113">Если ваш веб-сервер принимает пользовательские данные и вставляет их в возвращаемую веб-страницу, то, например, он может включать **\<script>** тег и запускать его как на сервере.</span><span class="sxs-lookup"><span data-stu-id="96bad-113">If your Web server takes user data and inserts it into the returned Web page, it might, for example, include a **\<script>** tag and run as if from the server.</span></span>

- <span data-ttu-id="96bad-114">Помните, что клиент может запросить любой URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="96bad-114">Remember that the client can request any URL.</span></span>

- <span data-ttu-id="96bad-115">Рассмотрим сложные и некорректные пути:</span><span class="sxs-lookup"><span data-stu-id="96bad-115">Consider tricky or invalid paths:</span></span>

  - <span data-ttu-id="96bad-116">..\ , пути очень большой длины;</span><span class="sxs-lookup"><span data-stu-id="96bad-116">..\ , extremely long paths.</span></span>

  - <span data-ttu-id="96bad-117">Использование подстановочных знаков (\*).</span><span class="sxs-lookup"><span data-stu-id="96bad-117">Use of wild card characters (\*).</span></span>

  - <span data-ttu-id="96bad-118">Расширение токена (%token%).</span><span class="sxs-lookup"><span data-stu-id="96bad-118">Token expansion (%token%).</span></span>

  - <span data-ttu-id="96bad-119">Необычные пути, имеющие специальное значение.</span><span class="sxs-lookup"><span data-stu-id="96bad-119">Strange forms of paths with special meaning.</span></span>

  - <span data-ttu-id="96bad-120">Альтернативные имена потоков файловой системы, например `filename::$DATA`.</span><span class="sxs-lookup"><span data-stu-id="96bad-120">Alternate file system stream names such as `filename::$DATA`.</span></span>

  - <span data-ttu-id="96bad-121">Короткие имена файлов, такие как `longfi~1` для `longfilename`.</span><span class="sxs-lookup"><span data-stu-id="96bad-121">Short versions of file names such as `longfi~1` for `longfilename`.</span></span>

- <span data-ttu-id="96bad-122">Помните, что Eval(userdata) может выполнять любые операции.</span><span class="sxs-lookup"><span data-stu-id="96bad-122">Remember that Eval(userdata) can do anything.</span></span>

- <span data-ttu-id="96bad-123">Будьте осторожны при позднем связывании с именем, которое содержит какие-либо пользовательские данные.</span><span class="sxs-lookup"><span data-stu-id="96bad-123">Be wary of late binding to a name that includes some user data.</span></span>

- <span data-ttu-id="96bad-124">Если вы имеете дело с веб-данными, проверьте на допустимость различные формы escape-последовательностей, включая:</span><span class="sxs-lookup"><span data-stu-id="96bad-124">If you are dealing with Web data, consider the various forms of escapes that are permissible, including:</span></span>

  - <span data-ttu-id="96bad-125">Шестнадцатеричные escape-последовательности (%nn).</span><span class="sxs-lookup"><span data-stu-id="96bad-125">Hexadecimal escapes (%nn).</span></span>

  - <span data-ttu-id="96bad-126">escape-последовательности Юникода (%nnn).</span><span class="sxs-lookup"><span data-stu-id="96bad-126">Unicode escapes (%nnn).</span></span>

  - <span data-ttu-id="96bad-127">Специальные символы увеличенной длины в UTF-8 (%nn%nn).</span><span class="sxs-lookup"><span data-stu-id="96bad-127">Overlong UTF-8 escapes (%nn%nn).</span></span>

  - <span data-ttu-id="96bad-128">Двойные escape-последовательности (%nn становится %mmnn, где %mm — escape-последовательность для "%").</span><span class="sxs-lookup"><span data-stu-id="96bad-128">Double escapes (%nn becomes %mmnn, where %mm is the escape for '%').</span></span>

- <span data-ttu-id="96bad-129">Будьте осторожны с именами пользователей, которые могут иметь несколько канонических форматов.</span><span class="sxs-lookup"><span data-stu-id="96bad-129">Be wary of user names that might have more than one canonical format.</span></span> <span data-ttu-id="96bad-130">Например, часто можно использовать либо формат ДОМЕН\\*имя_пользователя*, либо формат *имя_пользователя*@mydomain.example.com.</span><span class="sxs-lookup"><span data-stu-id="96bad-130">For example, you can often use either the MYDOMAIN\\*username* form or the *username*@mydomain.example.com form.</span></span>

## <a name="see-also"></a><span data-ttu-id="96bad-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="96bad-131">See also</span></span>

- [<span data-ttu-id="96bad-132">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="96bad-132">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)
- [<span data-ttu-id="96bad-133">Безопасность ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="96bad-133">ASP.NET Core Security</span></span>](/aspnet/core/security/)
