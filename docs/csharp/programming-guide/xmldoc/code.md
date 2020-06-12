---
title: <code> - C# programming guide
ms.date: 07/20/2015
f1_keywords:
- code
- <code>
helpviewer_keywords:
- code XML tag
- <code> C# XML tag
ms.assetid: f235e3bc-a709-43cf-8a9f-bd57cabdf6da
ms.openlocfilehash: 52d4b6caa0ea9e1a2d0212398f86374bc8af0402
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287445"
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
