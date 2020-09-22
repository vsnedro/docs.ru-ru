---
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 37b110cc6e12f11196d2a1c5cc6026d87b453626
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866405"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="42447-101">\<returns> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="42447-101">\<returns> (Visual Basic)</span></span>

<span data-ttu-id="42447-102">Задает возвращаемое значение свойства или функции.</span><span class="sxs-lookup"><span data-stu-id="42447-102">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42447-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42447-103">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="42447-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="42447-104">Parameters</span></span>  

 `description`  
 <span data-ttu-id="42447-105">Описание возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="42447-105">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42447-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="42447-106">Remarks</span></span>  

 <span data-ttu-id="42447-107">Используйте `<returns>` тег в комментарии для объявления метода, чтобы описать возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="42447-107">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="42447-108">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="42447-108">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42447-109">Пример</span><span class="sxs-lookup"><span data-stu-id="42447-109">Example</span></span>  

 <span data-ttu-id="42447-110">В этом примере `<returns>` тег используется для объяснения того, что `DoesRecordExist` возвращает функция.</span><span class="sxs-lookup"><span data-stu-id="42447-110">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="42447-111">См. также</span><span class="sxs-lookup"><span data-stu-id="42447-111">See also</span></span>

- [<span data-ttu-id="42447-112">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="42447-112">XML Comment Tags</span></span>](index.md)
