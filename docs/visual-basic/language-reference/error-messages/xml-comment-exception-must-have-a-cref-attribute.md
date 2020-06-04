---
title: Исключение комментария XML должно иметь атрибут cref
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: c498675ab6ae616fb63d3d76ef60bcac7e247145
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406512"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="2d322-102">Исключение комментария XML должно иметь атрибут cref</span><span class="sxs-lookup"><span data-stu-id="2d322-102">XML comment exception must have a 'cref' attribute</span></span>

<span data-ttu-id="2d322-103">\<exception>Тег предоставляет способ документирования исключений, которые могут быть вызваны методом.</span><span class="sxs-lookup"><span data-stu-id="2d322-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="2d322-104">Атрибут Required `cref` указывает имя члена, который проверяется генератором документации.</span><span class="sxs-lookup"><span data-stu-id="2d322-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="2d322-105">Если элемент существует, он преобразуется в каноническое имя элемента в файле документации.</span><span class="sxs-lookup"><span data-stu-id="2d322-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>

<span data-ttu-id="2d322-106">**Идентификатор ошибки:** BC42319</span><span class="sxs-lookup"><span data-stu-id="2d322-106">**Error ID:** BC42319</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="2d322-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2d322-107">To correct this error</span></span>

<span data-ttu-id="2d322-108">Добавьте `cref` атрибут к исключению следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2d322-108">Add the `cref` attribute to the exception as follows:</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a><span data-ttu-id="2d322-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2d322-109">See also</span></span>

- [\<exception>](../xmldoc/exception.md)
- [<span data-ttu-id="2d322-110">Практическое руководство. Создание XML-документации</span><span class="sxs-lookup"><span data-stu-id="2d322-110">How to: Create XML Documentation</span></span>](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="2d322-111">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="2d322-111">XML Comment Tags</span></span>](../xmldoc/index.md)
