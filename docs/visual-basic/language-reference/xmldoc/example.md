---
title: <example>
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 42f40581d252956433165789d6674234a295867c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400151"
---
# <a name="example-visual-basic"></a><span data-ttu-id="649ee-101">\<example> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="649ee-101">\<example> (Visual Basic)</span></span>
<span data-ttu-id="649ee-102">Указывает пример для элемента.</span><span class="sxs-lookup"><span data-stu-id="649ee-102">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="649ee-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="649ee-103">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a><span data-ttu-id="649ee-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="649ee-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="649ee-105">Описание примера кода.</span><span class="sxs-lookup"><span data-stu-id="649ee-105">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="649ee-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="649ee-106">Remarks</span></span>  
 <span data-ttu-id="649ee-107">`<example>`Тег позволяет указать пример использования метода или другого элемента библиотеки.</span><span class="sxs-lookup"><span data-stu-id="649ee-107">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="649ee-108">Обычно это касается использования [\<code>](code.md) тега.</span><span class="sxs-lookup"><span data-stu-id="649ee-108">This commonly involves using the [\<code>](code.md) tag.</span></span>  
  
 <span data-ttu-id="649ee-109">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="649ee-109">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="649ee-110">Пример</span><span class="sxs-lookup"><span data-stu-id="649ee-110">Example</span></span>  
 <span data-ttu-id="649ee-111">В этом примере `<example>` тег используется для включения примера использования `ID` поля.</span><span class="sxs-lookup"><span data-stu-id="649ee-111">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="649ee-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="649ee-112">See also</span></span>

- [<span data-ttu-id="649ee-113">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="649ee-113">XML Comment Tags</span></span>](index.md)
