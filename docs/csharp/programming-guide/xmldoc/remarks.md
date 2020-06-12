---
title: <remarks> Руководство по программированию на C#.
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: 739027786e02e559d86f990bf614e261b497c76f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287289"
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
