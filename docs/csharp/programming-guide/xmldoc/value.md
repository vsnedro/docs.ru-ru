---
title: <value> Руководство по программированию на C#.
description: Сведения о теге <value> в XML. Этот тег позволяет описать значение, которое представляется свойством.
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: d8294b477d7067653c71d1ec2047a85a0bfe6d02
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380778"
---
# <a name="value-c-programming-guide"></a>\<value> (руководство по программированию на C#)

## <a name="syntax"></a>Синтаксис

```xml
<value>property-description</value>
```

## <a name="parameters"></a>Параметры

- `property-description`

  Описание свойства.

## <a name="remarks"></a>Примечания

Тег `<value>` позволяет описывать значение, которое представляется свойством. При добавлении свойства с помощью мастера создания кода из среды разработки Visual Studio .NET для нового свойства будет добавлен тег [\<summary>](./summary.md). После этого следует вручную добавить тег `<value>` для описания значения, которое представляется свойством.

Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).

## <a name="example"></a>Пример

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
