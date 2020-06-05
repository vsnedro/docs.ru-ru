---
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: d325d5f9fbfd132630cf280653be214a267a7a80
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400064"
---
# <a name="param-visual-basic"></a><span data-ttu-id="30290-101">\<param> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30290-101">\<param> (Visual Basic)</span></span>
<span data-ttu-id="30290-102">Определяет имя и описание параметра.</span><span class="sxs-lookup"><span data-stu-id="30290-102">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30290-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30290-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="30290-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="30290-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="30290-105">Имя параметра метода.</span><span class="sxs-lookup"><span data-stu-id="30290-105">The name of a method parameter.</span></span> <span data-ttu-id="30290-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="30290-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="30290-107">Описание параметра.</span><span class="sxs-lookup"><span data-stu-id="30290-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30290-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="30290-108">Remarks</span></span>  
 <span data-ttu-id="30290-109">`<param>`Тег должен использоваться в комментариях для объявления метода, чтобы описать один из параметров для метода.</span><span class="sxs-lookup"><span data-stu-id="30290-109">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="30290-110">Текст для `<param>` тега будет отображаться в следующих местах:</span><span class="sxs-lookup"><span data-stu-id="30290-110">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
- <span data-ttu-id="30290-111">Сведения о параметрах IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="30290-111">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="30290-112">Дополнительные сведения см. в разделе [Using IntelliSense](/visualstudio/ide/using-intellisense).</span><span class="sxs-lookup"><span data-stu-id="30290-112">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
- <span data-ttu-id="30290-113">Обозреватель объектов.</span><span class="sxs-lookup"><span data-stu-id="30290-113">Object Browser.</span></span> <span data-ttu-id="30290-114">Дополнительные сведения см. [в разделе Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="30290-114">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="30290-115">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="30290-115">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30290-116">Пример</span><span class="sxs-lookup"><span data-stu-id="30290-116">Example</span></span>  
 <span data-ttu-id="30290-117">В этом примере `<param>` для описания параметра используется тег `id` .</span><span class="sxs-lookup"><span data-stu-id="30290-117">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="30290-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="30290-118">See also</span></span>

- [<span data-ttu-id="30290-119">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="30290-119">XML Comment Tags</span></span>](index.md)
