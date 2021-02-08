---
description: 'Подробнее: Рекомендуемые XML-теги для комментариев к документации (Visual Basic)'
title: Рекомендуемые XML-теги для комментариев документации
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 5d3451d98b66817de143cfbddbcb6121de57ca8b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787452"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>Рекомендуется использовать XML-теги для комментариев документации (Visual Basic)

Компилятор Visual Basic может обрабатывать комментарии документации в коде в XML-файле. Для обработки XML-файла в документации можно использовать дополнительные средства.  
  
 Комментарии XML разрешены в конструкциях кода, таких как типы и члены типов. Для разделяемых типов только одна часть типа может содержать комментарии XML, хотя не существует ограничений на комментирование его элементов.  
  
> [!NOTE]
> Комментарии к документации нельзя применять к пространствам имен. Причина состоит в том, что одно пространство имен может охватывать несколько сборок, и не все сборки должны быть загружены одновременно.  
  
 Компилятор обрабатывает любой тег, который является допустимым XML. Следующие теги предоставляют часто используемые функции в пользовательской документации.  
  
||||  
|---|---|---|  
|[\<c>](c.md)|[\<code>](code.md)|[\<example>](example.md)|  
|[\<exception>](exception.md)<sup>1</sup>|[\<include>](include.md)<sup>1</sup>|[\<list>](list.md)|  
|[\<para>](para.md)|[\<param>](param.md)<sup>1</sup>|[\<paramref>](paramref.md)|  
|[\<permission>](permission.md)<sup>1</sup>|[\<remarks>](remarks.md)|[\<returns>](returns.md)|  
|[\<see>](see.md)<sup>1</sup>|[\<seealso>](seealso.md)<sup>1</sup>|[\<summary>](summary.md)|  
|[\<typeparam>](typeparam.md)<sup>1</sup>|[\<value>](value.md)||  
  
 (<sup>1</sup> компилятор проверяет синтаксис.)  
  
> [!NOTE]
> Если необходимо, чтобы угловые скобки отображались в тексте комментария к документации, используйте `&lt;` и `&gt;` . Например, строка `"&lt;text in angle brackets&gt;"` будет выглядеть так `<text in angle brackets>` :.  
  
## <a name="see-also"></a>См. также

- [Документирование кода с помощью XML](../../programming-guide/program-structure/documenting-your-code-with-xml.md)
- [-doc](../../reference/command-line-compiler/doc.md)
- [Практическое руководство. Создание XML-документации](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
