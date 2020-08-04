---
title: Руководство по программированию на C#. Комментарии XML-документации
description: Сведения о комментариях XML-документации. Вы можете создавать документацию для кода, включив XML-элементы в специальные поля комментариев.
ms.date: 07/20/2015
f1_keywords:
- cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
ms.openlocfilehash: fbdeb53331d9fc63d24a3322ea13863d7c0a3630
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381883"
---
# <a name="xml-documentation-comments-c-programming-guide"></a>Руководство по программированию на C#. Комментарии XML-документации

В C# можно создавать документацию для кода путем включения XML-элементов в специальные поля комментариев (начинающиеся с трех символов косой черты) в исходном коде непосредственно перед блоком кода, к которому относятся комментарии. Например:

```csharp
/// <summary>
///  This class performs an important function.
/// </summary>
public class MyClass {}
```

При выполнении компиляции с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md) компилятор осуществляет поиск всех тегов XML в исходном коде и создает XML-файл документации. Для создания окончательной документации на основе сгенерированного компилятором файла можно создать пользовательское средство или применить такие средства, как [DocFX](https://dotnet.github.io/docfx/) или [Sandcastle](https://github.com/EWSoftware/SHFB).

Для ссылки на XML-элементы (например, если функция обрабатывает определенные XML-элементы, которые требуется включить в комментарии XML-документации) можно использовать стандартный механизм заключения в скобки (`<` и `>`).  Для ссылки на универсальные идентификаторы в элементах ссылок кода (`cref`) можно использовать escape-символы (например, `cref="List&lt;T&gt;"`) или фигурные скобки (`cref="List{T}"`).  В особом случае компилятор анализирует фигурные скобки, как угловые, чтобы при ссылке на универсальные идентификаторы сделать комментарий документации менее громоздким.

> [!NOTE]
> Комментарии XML-документации не являются метаданными. Они не включаются в скомпилированную сборку, и поэтому не доступны посредством отражения.

## <a name="in-this-section"></a>Содержание раздела

- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)

- [Обработка XML-файла](./processing-the-xml-file.md)

- [Разделители для тегов документации](./delimiters-for-documentation-tags.md)

- [Практическое руководство. Использование XML-документации](./how-to-use-the-xml-documentation-features.md)

## <a name="related-sections"></a>Связанные разделы

Дополнительные сведения можно найти в разделе

- [-doc (обработка комментариев документации)](../../language-reference/compiler-options/doc-compiler-option.md)

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
