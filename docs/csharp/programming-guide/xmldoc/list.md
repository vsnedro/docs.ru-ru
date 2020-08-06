---
title: <list> Руководство по программированию на C#.
description: Сведения о теге <list> XML. Этот тег используется для создания таблиц и определений, маркированных или нумерованных списков с помощью блоков item.
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: 361c2e6f343554a9b8519c3b2e41219b209e682d
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381870"
---
# <a name="list-c-programming-guide"></a>\<list> (руководство по программированию на C#)

## <a name="syntax"></a>Синтаксис

```xml
<list type="bullet|number|table">
    <listheader>
        <term>term</term>
        <description>description</description>
    </listheader>
    <item>
        <term>term</term>
        <description>description</description>
    </item>
</list>
```

## <a name="parameters"></a>Параметры

- `term`

  Термин, который будет определен в `description`.

- `description`

  Либо элемент маркированного или нумерованного списка, либо определение `term`.
  
## <a name="remarks"></a>Примечания

Блок `<listheader>` используется для определения строки заголовка в таблице или списке определений. При определении таблицы необходимо ввести данные для термина в заголовке.

Каждый элемент в списке указывается в блоке `<item>`. При создании списка определений необходимо указать одновременно `term` и `description`. Тем не менее для таблицы, маркированного или нумерованного списка достаточно ввести только `description`.

Число блоков `<item>` в списке или таблице не ограничено.

Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).

## <a name="example"></a>Пример

[!code-csharp[csProgGuideDocComments#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#6)]

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
