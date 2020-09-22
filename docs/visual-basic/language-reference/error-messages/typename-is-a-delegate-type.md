---
title: <typename> является типом делегата
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 4cc0a1221dcf65aa2a16fd7d82568c8544f27fdb
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875090"
---
# <a name="typename-is-a-delegate-type"></a><span data-ttu-id="9cef6-102">\<typename> является типом делегата</span><span class="sxs-lookup"><span data-stu-id="9cef6-102">'\<typename>' is a delegate type</span></span>

<span data-ttu-id="9cef6-103">" \<typename> " является типом делегата.</span><span class="sxs-lookup"><span data-stu-id="9cef6-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="9cef6-104">Конструкция делегата позволяет использовать только одно выражение AddressOf в качестве списка аргументов.</span><span class="sxs-lookup"><span data-stu-id="9cef6-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="9cef6-105">Часто выражение AddressOf можно использовать вместо конструкции делегата.</span><span class="sxs-lookup"><span data-stu-id="9cef6-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="9cef6-106">`New`Предложение, создающее экземпляр класса делегата, предоставляет конструктору делегата недопустимый список аргументов.</span><span class="sxs-lookup"><span data-stu-id="9cef6-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="9cef6-107">`AddressOf`При создании нового экземпляра делегата можно указать только одно выражение.</span><span class="sxs-lookup"><span data-stu-id="9cef6-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="9cef6-108">Эта ошибка может возникнуть, если вы не передаете аргументы конструктору делегата, если передаете несколько аргументов или передаете один аргумент, который не является допустимым `AddressOf` выражением.</span><span class="sxs-lookup"><span data-stu-id="9cef6-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="9cef6-109">**Идентификатор ошибки:** BC32008</span><span class="sxs-lookup"><span data-stu-id="9cef6-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9cef6-110">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9cef6-110">To correct this error</span></span>  
  
- <span data-ttu-id="9cef6-111">Используйте одно `AddressOf` выражение в списке аргументов для класса делегата в `New` предложении.</span><span class="sxs-lookup"><span data-stu-id="9cef6-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cef6-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9cef6-112">See also</span></span>

- [<span data-ttu-id="9cef6-113">Оператор New</span><span class="sxs-lookup"><span data-stu-id="9cef6-113">New Operator</span></span>](../operators/new-operator.md)
- [<span data-ttu-id="9cef6-114">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="9cef6-114">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="9cef6-115">Делегаты</span><span class="sxs-lookup"><span data-stu-id="9cef6-115">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="9cef6-116">Практическое руководство. Вызов метода делегата</span><span class="sxs-lookup"><span data-stu-id="9cef6-116">How to: Invoke a Delegate Method</span></span>](../../programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
