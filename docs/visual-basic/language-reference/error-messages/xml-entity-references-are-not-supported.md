---
description: 'Дополнительные сведения о: BC31180: ссылки на сущности XML не поддерживаются'
title: Ссылки на XML-сущности не поддерживаются
ms.date: 07/20/2015
f1_keywords:
- vbc31180
- bc31180
helpviewer_keywords:
- BC31180
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
ms.openlocfilehash: c45202fbd97d2343caf6bf4cdccf9368d0a7a295
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701421"
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
