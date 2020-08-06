---
title: <example> Руководство по программированию на C#.
description: Сведения о теге <example> в XML. Этот тег позволяет указать пример использования метода или другого элемента библиотеки.
ms.date: 07/20/2015
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C# XML tag
- example C# XML tag
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
ms.openlocfilehash: dd529e8f2a54cf9086d0d8c555dd1adb70b99126
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381532"
---
# <a name="example-c-programming-guide"></a>\<example> (руководство по программированию на C#)

## <a name="syntax"></a>Синтаксис

```xml
<example>description</example>
```

## <a name="parameters"></a>Параметры

- `description`

  Описание примера кода.

## <a name="remarks"></a>Примечания

Тег `<example>` позволяет указать пример использования метода или другого элемента библиотеки. Вместе с ним часто применяется тег [\<code>](./code.md).

Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).

## <a name="example"></a>Пример

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
