---
title: Ссылки на XML-сущности не поддерживаются
ms.date: 07/20/2015
f1_keywords:
- vbc31180
- bc31180
helpviewer_keywords:
- BC31180
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
ms.openlocfilehash: 37e72dbd6de61a50b4192a0151db40cb4be49d1c
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163276"
---
# <a name="bc31180-xml-entity-references-are-not-supported"></a>BC31180: ссылки на сущности XML не поддерживаются

Ссылка на сущность (например, `©` ), не определенная в спецификации xml 1,0, включается в качестве значения XML-литерала. `&` `"` `<` `>` `'` В XML-литералах поддерживаются только ссылки на XML-сущности,,, и.

 **Идентификатор ошибки:** BC31180

## <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите неподдерживаемую ссылку на сущность.

## <a name="see-also"></a>См. также

- [XML-литералы и спецификация XML 1.0](../../programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)
- [XML-литералы](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
