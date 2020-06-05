---
title: Практическое руководство. Создание XML-документации
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 1421cc85beba42b3cf3656c34b1d02347fbaf164
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403243"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>Практическое руководство. Создание XML-документации в Visual Basic

В этом примере показано, как добавить комментарии XML-документации в код.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-xml-documentation-for-a-type-or-member"></a>Создание XML-документации для типа или члена

1. В **редакторе кода**поместите курсор в строку над типом или членом, для которого требуется создать документацию.

2. Тип `'''` (три одинарные кавычки).

    В **редакторе кода**ДОБАВЛЯЕТСЯ XML-схема для типа или члена.

3. Добавьте описательные сведения между соответствующими тегами.

    > [!NOTE]
    > При добавлении дополнительных строк в блок XML-документации каждая строка должна начинаться с `'''` .

4. Добавьте дополнительный код, который использует тип или член с новыми комментариями XML-документации.

    IntelliSense отображает текст из \<summary> тега для типа или члена.

5. Скомпилируйте код, чтобы создать XML-файл, содержащий комментарии к документации. Дополнительные сведения см. в разделе [-doc](../../reference/command-line-compiler/doc.md).

## <a name="see-also"></a>См. также

- [Документирование кода с помощью XML](documenting-your-code-with-xml.md)
- [XML-теги для комментариев](../../language-reference/xmldoc/index.md)
- [-doc](../../reference/command-line-compiler/doc.md)
