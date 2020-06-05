---
title: Переменные структуры
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 270e8ca26185e4a68def3b95f4ce6ab4c57a629c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393589"
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="06b92-102">Переменные структуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06b92-102">Structure Variables (Visual Basic)</span></span>

<span data-ttu-id="06b92-103">После создания структуры можно объявить переменные уровня процедуры и модуля в качестве этого типа.</span><span class="sxs-lookup"><span data-stu-id="06b92-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="06b92-104">Например, можно создать структуру, которая записывает сведения о компьютерной системе.</span><span class="sxs-lookup"><span data-stu-id="06b92-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="06b92-105">Это продемонстрировано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="06b92-105">The following example demonstrates this.</span></span>

```vb
Public Structure systemInfo
    Public cPU As String
    Public memory As Long
    Public purchaseDate As Date
End Structure
```

<span data-ttu-id="06b92-106">Теперь можно объявлять переменные этого типа.</span><span class="sxs-lookup"><span data-stu-id="06b92-106">You can now declare variables of that type.</span></span> <span data-ttu-id="06b92-107">Это показано в следующем объявлении.</span><span class="sxs-lookup"><span data-stu-id="06b92-107">The following declaration illustrates this.</span></span>

```vb
Dim mySystem, yourSystem As systemInfo
```

> [!NOTE]
> <span data-ttu-id="06b92-108">В классах и модулях структуры, объявленные с помощью [инструкции Dim](../../../language-reference/statements/dim-statement.md) , по умолчанию имеют открытый доступ.</span><span class="sxs-lookup"><span data-stu-id="06b92-108">In classes and modules, structures declared using the [Dim Statement](../../../language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="06b92-109">Если структура должна быть закрытой, убедитесь, что она объявлена с помощью ключевого слова [Private](../../../language-reference/modifiers/private.md) .</span><span class="sxs-lookup"><span data-stu-id="06b92-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../language-reference/modifiers/private.md) keyword.</span></span>

## <a name="access-to-structure-values"></a><span data-ttu-id="06b92-110">Доступ к значениям структуры</span><span class="sxs-lookup"><span data-stu-id="06b92-110">Access to Structure Values</span></span>

<span data-ttu-id="06b92-111">Для присвоения и извлечения значений из элементов переменной структуры используется тот же синтаксис, что и при использовании для задания и получения свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="06b92-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="06b92-112">Оператор доступа к членам () размещается `.` между именем переменной структуры и именем элемента.</span><span class="sxs-lookup"><span data-stu-id="06b92-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="06b92-113">В следующем примере осуществляется доступ к элементам переменных, ранее объявленных как тип `systemInfo` .</span><span class="sxs-lookup"><span data-stu-id="06b92-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>

```vb
mySystem.cPU = "486"
Dim tooOld As Boolean
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True
```

## <a name="assigning-structure-variables"></a><span data-ttu-id="06b92-114">Присваивание переменных структуры</span><span class="sxs-lookup"><span data-stu-id="06b92-114">Assigning Structure Variables</span></span>

<span data-ttu-id="06b92-115">Можно также присвоить одну переменную другой, если оба имеют один и тот же тип структуры.</span><span class="sxs-lookup"><span data-stu-id="06b92-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="06b92-116">Все элементы одной структуры копируются в соответствующие элементы в другом.</span><span class="sxs-lookup"><span data-stu-id="06b92-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="06b92-117">Это показано в следующем объявлении.</span><span class="sxs-lookup"><span data-stu-id="06b92-117">The following declaration illustrates this.</span></span>

```vb
yourSystem = mySystem
```

<span data-ttu-id="06b92-118">Если элемент структуры является ссылочным типом, таким как массив типа `String` , `Object` или, то копируется указатель на данные.</span><span class="sxs-lookup"><span data-stu-id="06b92-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="06b92-119">В предыдущем примере, если `systemInfo` была включена объектная переменная, в предыдущем примере был скопирован указатель из `mySystem` в `yourSystem` , а изменение данных объекта через одну структуру вступит в действие при доступе через другую структуру.</span><span class="sxs-lookup"><span data-stu-id="06b92-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="06b92-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="06b92-120">See also</span></span>

- [<span data-ttu-id="06b92-121">Типы данных</span><span class="sxs-lookup"><span data-stu-id="06b92-121">Data Types</span></span>](index.md)
- [<span data-ttu-id="06b92-122">Простые типы данных</span><span class="sxs-lookup"><span data-stu-id="06b92-122">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="06b92-123">Составные типы данных</span><span class="sxs-lookup"><span data-stu-id="06b92-123">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="06b92-124">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="06b92-124">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="06b92-125">Структуры</span><span class="sxs-lookup"><span data-stu-id="06b92-125">Structures</span></span>](structures.md)
- [<span data-ttu-id="06b92-126">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="06b92-126">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="06b92-127">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="06b92-127">How to: Declare a Structure</span></span>](how-to-declare-a-structure.md)
- [<span data-ttu-id="06b92-128">Структуры и другие элементы программирования</span><span class="sxs-lookup"><span data-stu-id="06b92-128">Structures and Other Programming Elements</span></span>](structures-and-other-programming-elements.md)
- [<span data-ttu-id="06b92-129">Структуры и классы</span><span class="sxs-lookup"><span data-stu-id="06b92-129">Structures and Classes</span></span>](structures-and-classes.md)
- [<span data-ttu-id="06b92-130">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="06b92-130">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
