---
title: <code> - C# programming guide
description: Сведения о <code> tag. This tag is used to indicate multiple lines of code, while <c> marks single-line text in a description as code. в XML.
ms.date: 07/20/2015
f1_keywords:
- code
- <code>
helpviewer_keywords:
- code XML tag
- <code> C# XML tag
ms.assetid: f235e3bc-a709-43cf-8a9f-bd57cabdf6da
ms.openlocfilehash: f1f4cd930a876c8eca13de5f015e2b42b928d6f1
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382013"
---
# <a name="code-c-programming-guide"></a>\<code> (руководство по программированию на C#)

## <a name="syntax"></a>Синтаксис

```xml
<code>content</code>
```

## <a name="parameters"></a>Параметры

- `content`

  Текст, который необходимо пометить как код.

## <a name="remarks"></a>Примечания

Тег `<code>` используется для указания нескольких строк кода. С помощью тега [\<c>](./code-inline.md) можно указать, что однострочный текст в описании необходимо пометить как код.

Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).

## <a name="example"></a>Пример

Пример использования тега `<code>` см. в статье [\<example>](./example.md).

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
