---
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 19300a928a59c7259f81b282bd28d9bdd447d76b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872624"
---
# <a name="param-visual-basic"></a><span data-ttu-id="5cd2b-101">\<param> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5cd2b-101">\<param> (Visual Basic)</span></span>

<span data-ttu-id="5cd2b-102">Определяет имя и описание параметра.</span><span class="sxs-lookup"><span data-stu-id="5cd2b-102">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cd2b-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cd2b-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cd2b-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="5cd2b-104">Parameters</span></span>  

 `name`  
 <span data-ttu-id="5cd2b-105">Имя параметра метода.</span><span class="sxs-lookup"><span data-stu-id="5cd2b-105">The name of a method parameter.</span></span> <span data-ttu-id="5cd2b-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="5cd2b-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="5cd2b-107">Описание параметра.</span><span class="sxs-lookup"><span data-stu-id="5cd2b-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5cd2b-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="5cd2b-108">Remarks</span></span>  

 <span data-ttu-id="5cd2b-109">Тег `<param>` следует использовать в комментариях к объявлению метода для описания одного из параметров такого метода.</span><span class="sxs-lookup"><span data-stu-id="5cd2b-109">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="5cd2b-110">Текст для `<param>` тега будет отображаться в следующих местах:</span><span class="sxs-lookup"><span data-stu-id="5cd2b-110">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
- <span data-ttu-id="5cd2b-111">Сведения о параметрах IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="5cd2b-111">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="5cd2b-112">Дополнительные сведения см. в разделе [Using IntelliSense](/visualstudio/ide/using-intellisense).</span><span class="sxs-lookup"><span data-stu-id="5cd2b-112">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
- <span data-ttu-id="5cd2b-113">Обозреватель объектов.</span><span class="sxs-lookup"><span data-stu-id="5cd2b-113">Object Browser.</span></span> <span data-ttu-id="5cd2b-114">Дополнительные сведения см. [в разделе Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="5cd2b-114">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="5cd2b-115">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="5cd2b-115">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cd2b-116">Пример</span><span class="sxs-lookup"><span data-stu-id="5cd2b-116">Example</span></span>  

 <span data-ttu-id="5cd2b-117">В этом примере `<param>` для описания параметра используется тег `id` .</span><span class="sxs-lookup"><span data-stu-id="5cd2b-117">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="5cd2b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5cd2b-118">See also</span></span>

- [<span data-ttu-id="5cd2b-119">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="5cd2b-119">XML Comment Tags</span></span>](index.md)
