---
title: <example>
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 6e9f63e4d31df7790f51ae4d166b606f2c63f14b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872976"
---
# <a name="example-visual-basic"></a><span data-ttu-id="1f7b6-101">\<example> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f7b6-101">\<example> (Visual Basic)</span></span>

<span data-ttu-id="1f7b6-102">Указывает пример для элемента.</span><span class="sxs-lookup"><span data-stu-id="1f7b6-102">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f7b6-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f7b6-103">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f7b6-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="1f7b6-104">Parameters</span></span>  

 `description`  
 <span data-ttu-id="1f7b6-105">Описание примера кода.</span><span class="sxs-lookup"><span data-stu-id="1f7b6-105">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f7b6-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="1f7b6-106">Remarks</span></span>  

 <span data-ttu-id="1f7b6-107">Тег `<example>` позволяет указать пример использования метода или другого элемента библиотеки.</span><span class="sxs-lookup"><span data-stu-id="1f7b6-107">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="1f7b6-108">Вместе с ним часто применяется тег [\<code>](code.md).</span><span class="sxs-lookup"><span data-stu-id="1f7b6-108">This commonly involves using the [\<code>](code.md) tag.</span></span>  
  
 <span data-ttu-id="1f7b6-109">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="1f7b6-109">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f7b6-110">Пример</span><span class="sxs-lookup"><span data-stu-id="1f7b6-110">Example</span></span>  

 <span data-ttu-id="1f7b6-111">В этом примере `<example>` тег используется для включения примера использования `ID` поля.</span><span class="sxs-lookup"><span data-stu-id="1f7b6-111">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="1f7b6-112">См. также</span><span class="sxs-lookup"><span data-stu-id="1f7b6-112">See also</span></span>

- [<span data-ttu-id="1f7b6-113">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="1f7b6-113">XML Comment Tags</span></span>](index.md)
