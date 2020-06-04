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
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>Исключение комментария XML должно иметь атрибут cref

\<exception>Тег предоставляет способ документирования исключений, которые могут быть вызваны методом. Атрибут Required `cref` указывает имя члена, который проверяется генератором документации. Если элемент существует, он преобразуется в каноническое имя элемента в файле документации.

**Идентификатор ошибки:** BC42319

## <a name="to-correct-this-error"></a>Исправление ошибки

Добавьте `cref` атрибут к исключению следующим образом:

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a>См. также раздел

- [\<exception>](../xmldoc/exception.md)
- [Практическое руководство. Создание XML-документации](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML-теги для комментариев](../xmldoc/index.md)
