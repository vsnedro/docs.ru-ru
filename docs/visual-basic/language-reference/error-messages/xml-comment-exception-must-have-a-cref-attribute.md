---
description: 'Дополнительные сведения о: BC42319: Исключение комментария XML должно иметь атрибут cref'
title: Исключение комментария XML должно иметь атрибут cref
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: e602a2973d95f70d5ab532e6be319a9575d239a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701460"
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
