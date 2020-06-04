---
title: Недопустимый порядковый номер
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 7b9bd8435b56dd5e33d14eb35d76aacc7d60c8b5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413057"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="66880-102">Недопустимый порядковый номер</span><span class="sxs-lookup"><span data-stu-id="66880-102">Ordinal is not valid</span></span>
<span data-ttu-id="66880-103">При вызове библиотеки динамической компоновки (DLL) для использования числа вместо имени процедуры используется `#num` синтаксис.</span><span class="sxs-lookup"><span data-stu-id="66880-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="66880-104">Эта ошибка может быть вызвана следующими причинами.</span><span class="sxs-lookup"><span data-stu-id="66880-104">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="66880-105">Сбой при преобразовании `#num` выражения в порядковый номер.</span><span class="sxs-lookup"><span data-stu-id="66880-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
- <span data-ttu-id="66880-106">В `#num` указанном параметре не указана какая-либо функция в библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="66880-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
- <span data-ttu-id="66880-107">Библиотека типов содержит недопустимое объявление, что приводит к внутреннему использованию недопустимого порядкового номера.</span><span class="sxs-lookup"><span data-stu-id="66880-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="66880-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="66880-108">To correct this error</span></span>  
  
1. <span data-ttu-id="66880-109">Убедитесь, что выражение представляет допустимое число, или вызовите процедуру по имени.</span><span class="sxs-lookup"><span data-stu-id="66880-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2. <span data-ttu-id="66880-110">Убедитесь `#num` , что определяет допустимую функцию в библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="66880-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3. <span data-ttu-id="66880-111">Изолируйте вызов процедуры, который вызывает проблему, закомментируя код.</span><span class="sxs-lookup"><span data-stu-id="66880-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="66880-112">Напишите `Declare` инструкцию для процедуры и сообщите о проблеме поставщику библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="66880-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66880-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="66880-113">See also</span></span>

- [<span data-ttu-id="66880-114">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="66880-114">Declare Statement</span></span>](../statements/declare-statement.md)
