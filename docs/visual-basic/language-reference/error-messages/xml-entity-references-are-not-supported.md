---
title: Ссылки на XML-сущности не поддерживаются
ms.date: 07/20/2015
f1_keywords:
- vbc31180
- bc31180
helpviewer_keywords:
- BC31180
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
ms.openlocfilehash: 470e5577654ce8b6bbc2732a41c130a85ddc96e5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874999"
---
# <a name="xml-entity-references-are-not-supported"></a>Ссылки на XML-сущности не поддерживаются

Ссылка на сущность (например, `©` ), не определенная в спецификации xml 1,0, включается в качестве значения XML-литерала. `&` `"` `<` `>` `'` В XML-литералах поддерживаются только ссылки на XML-сущности,,, и.  
  
 **Идентификатор ошибки:** BC31180  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Удалите неподдерживаемую ссылку на сущность.  
  
## <a name="see-also"></a>См. также

- [XML-литералы и спецификация XML 1.0](../../programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)
- [XML-литералы](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
