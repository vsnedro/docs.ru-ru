---
title: Исключение комментария XML должно иметь атрибут cref
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 18e7aa5f6905eaa9c509aa21fe6f5bfcd54d46f0
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163302"
---
# <a name="bc42319-xml-comment-exception-must-have-a-cref-attribute"></a>BC42319: Исключение комментария XML должно иметь атрибут cref

\<exception>Тег предоставляет способ документирования исключений, которые могут быть вызваны методом. Атрибут Required `cref` указывает имя члена, который проверяется генератором документации. Если элемент существует, он преобразуется в каноническое имя элемента в файле документации.

**Идентификатор ошибки:** BC42319

## <a name="to-correct-this-error"></a>Исправление ошибки

Добавьте `cref` атрибут к исключению следующим образом:

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a>См. также

- [\<exception>](../xmldoc/exception.md)
- [Практическое руководство. Создание XML-документации](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML-теги для комментариев](../xmldoc/index.md)
