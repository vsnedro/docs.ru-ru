---
title: Ссылки на XML-сущности не поддерживаются
ms.date: 07/20/2015
f1_keywords:
- vbc31180
- bc31180
helpviewer_keywords:
- BC31180
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
ms.openlocfilehash: ae997d853a93999a3b29215ea1257da7a1d48c84
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406460"
---
# <a name="xml-entity-references-are-not-supported"></a>Ссылки на XML-сущности не поддерживаются
Ссылка на сущность (например, `©` ), не определенная в спецификации xml 1,0, включается в качестве значения XML-литерала. `&` `"` `<` `>` `'` В XML-литералах поддерживаются только ссылки на XML-сущности,,, и.  
  
 **Идентификатор ошибки:** BC31180  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Удалите неподдерживаемую ссылку на сущность.  
  
## <a name="see-also"></a>См. также раздел

- [XML-литералы и спецификация XML 1.0](../../programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)
- [XML-литералы](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
