---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 0e2051d1b00b881c06082b3af483890d8595899f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400077"
---
# <a name="para-visual-basic"></a><span data-ttu-id="5c939-101">\<para> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c939-101">\<para> (Visual Basic)</span></span>
<span data-ttu-id="5c939-102">Указывает, что содержимое форматируется как абзац.</span><span class="sxs-lookup"><span data-stu-id="5c939-102">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c939-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c939-103">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c939-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c939-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="5c939-105">Текст абзаца.</span><span class="sxs-lookup"><span data-stu-id="5c939-105">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c939-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="5c939-106">Remarks</span></span>  
 <span data-ttu-id="5c939-107">`<para>`Тег используется внутри тега, например, [\<summary>](summary.md) [\<remarks>](remarks.md) или [\<returns>](returns.md) , и позволяет добавить в текст структуру.</span><span class="sxs-lookup"><span data-stu-id="5c939-107">The `<para>` tag is for use inside a tag, such as [\<summary>](summary.md), [\<remarks>](remarks.md), or [\<returns>](returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="5c939-108">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="5c939-108">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c939-109">Пример</span><span class="sxs-lookup"><span data-stu-id="5c939-109">Example</span></span>  
 <span data-ttu-id="5c939-110">В этом примере `<para>` тег используется для разбиения раздела примечаний для `UpdateRecord` метода на два абзаца.</span><span class="sxs-lookup"><span data-stu-id="5c939-110">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="5c939-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5c939-111">See also</span></span>

- [<span data-ttu-id="5c939-112">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="5c939-112">XML Comment Tags</span></span>](index.md)
