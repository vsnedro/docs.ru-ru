---
title: <returns> Руководство по программированию на C#.
description: Сведения о теге <returns> в XML. Этот тег используется в комментариях к объявлению метода для описания возвращаемого значения.
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: e461d46df619a351048ae7942e59847d39e490f9
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381402"
---
# <a name="returns-c-programming-guide"></a>\<returns> (руководство по программированию на C#)

## <a name="syntax"></a>Синтаксис

```xml
<returns>description</returns>
```

## <a name="parameters"></a>Параметры

- `description`

  Описание возвращаемого значения.

## <a name="remarks"></a>Примечания

Тег `<returns>` следует использовать в комментариях к объявлению метода для описания возвращаемого значения.

Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).

## <a name="example"></a>Пример

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
