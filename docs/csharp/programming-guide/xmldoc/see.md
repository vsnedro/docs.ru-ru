---
title: Руководство по программированию на C#. <see>
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 731e42a6d4d354b043a56dbe150bb03a693a9454
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86863790"
---
# <a name="see-c-programming-guide"></a>\<see> (руководство по программированию на C#)

## <a name="syntax"></a>Синтаксис

```xml
<see cref="member"/>
```

## <a name="parameters"></a>Параметры

- cref = "`member`"

  Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции. Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных. *member* необходимо заключать в двойные кавычки (" ").

## <a name="remarks"></a>Примечания

Тег `<see>` позволяет задать ссылку из текста. С помощью тега [\<seealso>](./seealso.md) можно указать, что текст должен быть размещен в разделе "См. также". Используйте [cref Attribute](./cref-attribute.md) для создания внутренних гиперссылок на страницы документации для элементов кода. Кроме того, ``href`` является допустимым атрибутом, который будет функционировать как гиперссылка.

Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).

В следующем примере показан тег `<see>` в разделе сводки.

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
