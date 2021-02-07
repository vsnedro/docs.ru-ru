---
description: 'Дополнительные сведения о: BC31200: XML-литералы и XML-свойства не поддерживаются в внедренном коде в ASP.NET'
title: XML литералы и XML свойства не поддерживаются во встроенном в ASP.NET коде
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: 0a5328676ee38a56334b77f665a464daa586ce3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701408"
---
# <a name="bc31200-xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a>BC31200: XML-литералы и XML-свойства не поддерживаются в внедренном коде в ASP.NET

XML-литералы и XML-свойства не поддерживаются во внедренном коде в ASP.NET. Чтобы использовать функции XML, переместите код в код программной части.

 XML-литерал или свойство оси XML определяются внутри внедренного кода ( `<%= =>` ) в файле ASP.NET.

 **Идентификатор ошибки:** BC31200

## <a name="to-correct-this-error"></a>Исправление ошибки

- Переместите код, включающий XML-литерал или свойство оси XML, в файл кода программной части ASP.NET.

## <a name="see-also"></a>См. также

- [XML-литералы](../xml-literals/index.md)
- [Свойства оси XML](../xml-axis/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
