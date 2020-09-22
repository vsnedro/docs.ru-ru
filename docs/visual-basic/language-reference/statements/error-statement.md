---
title: Оператор Error
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: f3f9f5ecb96686fe525e98cf64672d81a3145796
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873273"
---
# <a name="error-statement"></a><span data-ttu-id="d2aff-102">Оператор Error</span><span class="sxs-lookup"><span data-stu-id="d2aff-102">Error Statement</span></span>

<span data-ttu-id="d2aff-103">Имитирует возникновение ошибки.</span><span class="sxs-lookup"><span data-stu-id="d2aff-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2aff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d2aff-104">Syntax</span></span>  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="d2aff-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="d2aff-105">Parts</span></span>  

 `errornumber`  
 <span data-ttu-id="d2aff-106">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d2aff-106">Required.</span></span> <span data-ttu-id="d2aff-107">Может быть любым допустимым номером ошибки.</span><span class="sxs-lookup"><span data-stu-id="d2aff-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2aff-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="d2aff-108">Remarks</span></span>  

 <span data-ttu-id="d2aff-109">Эта `Error` инструкция поддерживается для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="d2aff-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="d2aff-110">В новом коде, особенно при создании объектов, используйте `Err` `Raise` метод объекта для создания ошибок времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="d2aff-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="d2aff-111">Если `errornumber` определено, `Error` инструкция вызывает обработчик ошибок после того, как свойства `Err` объекта присвоены следующие значения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="d2aff-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="d2aff-112">Свойство</span><span class="sxs-lookup"><span data-stu-id="d2aff-112">Property</span></span>|<span data-ttu-id="d2aff-113">Значение</span><span class="sxs-lookup"><span data-stu-id="d2aff-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="d2aff-114">Значение, указанное в качестве аргумента `Error` инструкции.</span><span class="sxs-lookup"><span data-stu-id="d2aff-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="d2aff-115">Может быть любым допустимым номером ошибки.</span><span class="sxs-lookup"><span data-stu-id="d2aff-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="d2aff-116">Имя текущего проекта Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d2aff-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="d2aff-117">Строковое выражение, соответствующее возвращаемому значению `Error` функции для указанного объекта `Number` , если эта строка существует.</span><span class="sxs-lookup"><span data-stu-id="d2aff-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="d2aff-118">Если строка не существует, `Description` содержит строку нулевой длины ("").</span><span class="sxs-lookup"><span data-stu-id="d2aff-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="d2aff-119">Полный диск, путь и имя файла подходящего файла справки Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d2aff-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="d2aff-120">Соответствующий идентификатор контекста файла справки Visual Basic для ошибки, соответствующей `Number` свойству.</span><span class="sxs-lookup"><span data-stu-id="d2aff-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="d2aff-121">Ноль.</span><span class="sxs-lookup"><span data-stu-id="d2aff-121">Zero.</span></span>|  
  
 <span data-ttu-id="d2aff-122">Если обработчик ошибок не существует или не включен, сообщение об ошибке создается и отображается в `Err` свойствах объекта.</span><span class="sxs-lookup"><span data-stu-id="d2aff-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d2aff-123">Некоторые приложения Visual Basic узла не могут создавать объекты.</span><span class="sxs-lookup"><span data-stu-id="d2aff-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="d2aff-124">Чтобы определить, может ли он создавать классы и объекты, см. документацию по ведущему приложению.</span><span class="sxs-lookup"><span data-stu-id="d2aff-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2aff-125">Пример</span><span class="sxs-lookup"><span data-stu-id="d2aff-125">Example</span></span>  

 <span data-ttu-id="d2aff-126">В этом примере используется `Error` оператор для создания номера ошибки 11.</span><span class="sxs-lookup"><span data-stu-id="d2aff-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="d2aff-127">Требования</span><span class="sxs-lookup"><span data-stu-id="d2aff-127">Requirements</span></span>  

 <span data-ttu-id="d2aff-128">**Пространство имен:** [Microsoft. VisualBasic](../runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="d2aff-128">**Namespace:** [Microsoft.VisualBasic](../runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="d2aff-129">**Сборка:** Библиотека времени выполнения Visual Basic (в Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="d2aff-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2aff-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d2aff-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="d2aff-131">Оператор On Error</span><span class="sxs-lookup"><span data-stu-id="d2aff-131">On Error Statement</span></span>](on-error-statement.md)
- [<span data-ttu-id="d2aff-132">Оператор Resume</span><span class="sxs-lookup"><span data-stu-id="d2aff-132">Resume Statement</span></span>](resume-statement.md)
- [<span data-ttu-id="d2aff-133">Сообщения об ошибках</span><span class="sxs-lookup"><span data-stu-id="d2aff-133">Error Messages</span></span>](../error-messages/index.md)
