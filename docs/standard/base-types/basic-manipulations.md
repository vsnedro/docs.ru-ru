---
title: Базовые операции со строками в .NET
description: См. пример, который вызывает много строковых методов.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET], examples
ms.assetid: 121d1eae-251b-44c0-8818-57da04b8215e
ms.openlocfilehash: e3e969520e068bde234c13d45ad790b76ecf8fdb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825161"
---
# <a name="how-to-perform-basic-string-manipulations-in-net"></a><span data-ttu-id="a09bb-103">Практическое руководство. Выполнение базовых операций со строками в .NET</span><span class="sxs-lookup"><span data-stu-id="a09bb-103">How to: Perform Basic String Manipulations in .NET</span></span>

<span data-ttu-id="a09bb-104">В следующем примере некоторые методы, описанные в руководстве по [базовым операциям со строками](basic-string-operations.md), используются для создания класса, который выполняет обработку строк так же, как это происходит в реальном приложении.</span><span class="sxs-lookup"><span data-stu-id="a09bb-104">The following example uses some of the methods discussed in the [Basic String Operations](basic-string-operations.md) topics to construct a class that performs string manipulations in a manner that might be found in a real-world application.</span></span> <span data-ttu-id="a09bb-105">Класс `MailToData` хранит имя и адрес человека в отдельных свойствах и предоставляет способ объединения полей `City`, `State` и `Zip` в одну строку для отображения пользователю.</span><span class="sxs-lookup"><span data-stu-id="a09bb-105">The `MailToData` class stores the name and address of an individual in separate properties and provides a way to combine the `City`, `State`, and `Zip` fields into a single string for display to the user.</span></span> <span data-ttu-id="a09bb-106">Кроме того, при использовании этого класса пользователь может указать город, область и почтовый индекс в виде одной строки.</span><span class="sxs-lookup"><span data-stu-id="a09bb-106">Furthermore, the class allows the user to enter the city, state, and zip code information as a single string.</span></span> <span data-ttu-id="a09bb-107">Приложение автоматически анализирует одну строку и вводит соответствующие сведения в соответствующее свойство.</span><span class="sxs-lookup"><span data-stu-id="a09bb-107">The application automatically parses the single string and enters the proper information into the corresponding property.</span></span>

<span data-ttu-id="a09bb-108">В этом упрощенном примере используется консольное приложение с интерфейсом командной строки.</span><span class="sxs-lookup"><span data-stu-id="a09bb-108">For simplicity, this example uses a console application with a command-line interface.</span></span>

## <a name="example"></a><span data-ttu-id="a09bb-109">Пример</span><span class="sxs-lookup"><span data-stu-id="a09bb-109">Example</span></span>

[!code-csharp[Conceptual.String.BasicOps#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/basicops.cs#1)]
[!code-vb[Conceptual.String.BasicOps#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/basicops.vb#1)]

<span data-ttu-id="a09bb-110">При выполнении предыдущего кода пользователю предлагается ввести его имя и адрес.</span><span class="sxs-lookup"><span data-stu-id="a09bb-110">When the preceding code is executed, the user is asked to enter their name and address.</span></span> <span data-ttu-id="a09bb-111">Приложение размещает сведения в соответствующих свойствах и отображает их для пользователя, создавая одну строку, в которой представлены сведения о городе, области и почтовом индексе.</span><span class="sxs-lookup"><span data-stu-id="a09bb-111">The application places the information in the appropriate properties and displays the information back to the user, creating a single string that displays the city, state, and zip code information.</span></span>

## <a name="see-also"></a><span data-ttu-id="a09bb-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a09bb-112">See also</span></span>

- [<span data-ttu-id="a09bb-113">Базовые операции со строками в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a09bb-113">Basic String Operations</span></span>](basic-string-operations.md)
