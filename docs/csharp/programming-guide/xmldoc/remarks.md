---
title: <remarks> Руководство по программированию на C#.
description: Сведения о теге <remarks> в XML. Этот тег позволяет добавить сведения о типе, дополняющие информацию, которая указана с помощью <summary>.
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: d38905d100e24158e7a1412f6be9f01a7ced2382
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381506"
---
# <a name="remarks-c-programming-guide"></a>\<remarks> (руководство по программированию на C#)

## <a name="syntax"></a>Синтаксис

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a>Параметры

- `Description`

  Описание элемента.

## <a name="remarks"></a>Примечания

Тег `<remarks>` позволяет добавить сведения о типе, дополняющие информацию, указанную с помощью тега [\<summary>](./summary.md). Эти сведения отображаются в окне "Обозреватель объектов".

Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).

## <a name="example"></a>Пример

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
