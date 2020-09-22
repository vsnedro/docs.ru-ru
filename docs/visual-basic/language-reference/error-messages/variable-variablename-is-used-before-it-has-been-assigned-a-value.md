---
title: Переменная <variablename> используется до того, как ей присвоено значение
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: a60afe0907e974dfb345d20d18762cb5f84127d9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875029"
---
# <a name="variable-variablename-is-used-before-it-has-been-assigned-a-value"></a><span data-ttu-id="aecc7-102">Переменная \<variablename> используется до того, как ей присвоено значение</span><span class="sxs-lookup"><span data-stu-id="aecc7-102">Variable '\<variablename>' is used before it has been assigned a value</span></span>

<span data-ttu-id="aecc7-103">Переменная " \<variablename> " используется до того, как ей было присвоено значение.</span><span class="sxs-lookup"><span data-stu-id="aecc7-103">Variable '\<variablename>' is used before it has been assigned a value.</span></span> <span data-ttu-id="aecc7-104">Во время выполнения может возникнуть исключение "пустая ссылка".</span><span class="sxs-lookup"><span data-stu-id="aecc7-104">A null reference exception could result at run time.</span></span>  
  
 <span data-ttu-id="aecc7-105">Приложение имеет по крайней мере один возможный путь в коде, который считывает переменную, прежде чем ей будет присвоено значение.</span><span class="sxs-lookup"><span data-stu-id="aecc7-105">An application has at least one possible path through its code that reads a variable before any value is assigned to it.</span></span>  
  
 <span data-ttu-id="aecc7-106">Если переменной никогда не назначалось значение, она содержит значение по умолчанию для своего типа данных.</span><span class="sxs-lookup"><span data-stu-id="aecc7-106">If a variable has never been assigned a value, it holds the default value for its data type.</span></span> <span data-ttu-id="aecc7-107">Для ссылочного типа данных значение по умолчанию — [Nothing](../nothing.md).</span><span class="sxs-lookup"><span data-stu-id="aecc7-107">For a reference data type, that default value is [Nothing](../nothing.md).</span></span> <span data-ttu-id="aecc7-108">Чтение переменной ссылки, которая имеет значение `Nothing` , в некоторых случаях может привести к исключению <xref:System.NullReferenceException> .</span><span class="sxs-lookup"><span data-stu-id="aecc7-108">Reading a reference variable that has a value of `Nothing` can cause a <xref:System.NullReferenceException> in some circumstances.</span></span>  
  
 <span data-ttu-id="aecc7-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="aecc7-109">By default, this message is a warning.</span></span> <span data-ttu-id="aecc7-110">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="aecc7-110">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="aecc7-111">**Идентификатор ошибки:** BC42104</span><span class="sxs-lookup"><span data-stu-id="aecc7-111">**Error ID:** BC42104</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="aecc7-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="aecc7-112">To correct this error</span></span>  
  
- <span data-ttu-id="aecc7-113">Проверьте логику потока управления и убедитесь, что переменная имеет допустимое значение, прежде чем управление передается в любую инструкцию, которая ее считывает.</span><span class="sxs-lookup"><span data-stu-id="aecc7-113">Check your control flow logic and make sure the variable has a valid value before control passes to any statement that reads it.</span></span>  
  
- <span data-ttu-id="aecc7-114">Один из способов гарантировать, что переменная всегда имеет допустимое значение, — инициализировать ее как часть объявления.</span><span class="sxs-lookup"><span data-stu-id="aecc7-114">One way to guarantee that the variable always has a valid value is to initialize it as part of its declaration.</span></span> <span data-ttu-id="aecc7-115">См. раздел "Инициализация" в [операторе Dim](../statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aecc7-115">See "Initialization" in [Dim Statement](../statements/dim-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aecc7-116">См. также</span><span class="sxs-lookup"><span data-stu-id="aecc7-116">See also</span></span>

- [<span data-ttu-id="aecc7-117">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="aecc7-117">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="aecc7-118">Объявление переменной</span><span class="sxs-lookup"><span data-stu-id="aecc7-118">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="aecc7-119">Устранение неполадок, связанных с переменными</span><span class="sxs-lookup"><span data-stu-id="aecc7-119">Troubleshooting Variables</span></span>](../../programming-guide/language-features/variables/troubleshooting-variables.md)
