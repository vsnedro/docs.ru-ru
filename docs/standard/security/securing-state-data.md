---
title: Обеспечение безопасности данных
description: Объявите данные о состоянии как закрытые или внутренние переменные, чтобы ограничить доступ к ним. Доступ к таким данным по-прежнему можно получить с помощью отражения, сериализации и отладки.
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
ms.openlocfilehash: 849ed993befaceda1b04becbb7fb2530c5c62a77
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824165"
---
# <a name="securing-state-data"></a><span data-ttu-id="aadbe-104">Обеспечение безопасности данных</span><span class="sxs-lookup"><span data-stu-id="aadbe-104">Securing State Data</span></span>

<span data-ttu-id="aadbe-105">Приложения, работающие с конфиденциальными данными или принимающие любые решения по организации безопасности, должны сохранять эти данные под своим непосредственным управлением и не должны позволять потенциально вредоносному коду напрямую получать доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="aadbe-105">Applications that handle sensitive data or make any kind of security decisions need to keep that data under their own control and cannot allow other potentially malicious code to access the data directly.</span></span> <span data-ttu-id="aadbe-106">Лучшим способом защиты данных в памяти является объявление этих данных как закрытых или внутренних переменных (с областью, ограниченной той же сборкой).</span><span class="sxs-lookup"><span data-stu-id="aadbe-106">The best way to protect data in memory is to declare the data as private or internal (with scope limited to the same assembly) variables.</span></span> <span data-ttu-id="aadbe-107">Однако не следует забывать, что даже к этим данным применяются права доступа.</span><span class="sxs-lookup"><span data-stu-id="aadbe-107">However, even this data is subject to access you should be aware of:</span></span>  
  
- <span data-ttu-id="aadbe-108">С помощью механизмов отражения код с высоким доверием, способный ссылаться на ваш объект, может получать и устанавливать закрытые члены.</span><span class="sxs-lookup"><span data-stu-id="aadbe-108">Using reflection mechanisms, highly trusted code that can reference your object can get and set private members.</span></span>  
  
- <span data-ttu-id="aadbe-109">С помощью сериализации код с высоким доверием может эффективно получать и устанавливать закрытые члены, если он имеет доступ к соответствующим данным в сериализованной форме объекта.</span><span class="sxs-lookup"><span data-stu-id="aadbe-109">Using serialization, highly trusted code can effectively get and set private members if it can access the corresponding data in the serialized form of the object.</span></span>  
  
- <span data-ttu-id="aadbe-110">Эти данные могут считываться в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="aadbe-110">Under debugging, this data can be read.</span></span>  
  
 <span data-ttu-id="aadbe-111">Убедитесь, что ни один из ваших собственных методов или свойств не предоставляет непреднамеренно эти значения.</span><span class="sxs-lookup"><span data-stu-id="aadbe-111">Make sure none of your own methods or properties exposes these values unintentionally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aadbe-112">См. также статью</span><span class="sxs-lookup"><span data-stu-id="aadbe-112">See also</span></span>

- [<span data-ttu-id="aadbe-113">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="aadbe-113">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)
- [<span data-ttu-id="aadbe-114">Безопасность ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="aadbe-114">ASP.NET Core Security</span></span>](/aspnet/core/security/)
