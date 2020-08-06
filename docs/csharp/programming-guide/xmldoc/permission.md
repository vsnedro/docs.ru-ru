---
title: <permission> Руководство по программированию на C#.
description: Узнайте о теге <permission> XML. Этот тег позволяет документировать доступ члена, а класс PermissionSet позволяет определить доступ к члену.
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 38c87505b8b2973875e474ffd296dc02b7fb9de6
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381727"
---
# <a name="permission-c-programming-guide"></a>\<permission> (руководство по программированию на C#)

## <a name="syntax"></a>Синтаксис

```xml
<permission cref="member">description</permission>
```

## <a name="parameters"></a>Параметры

- cref = "`member`"

  Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции. Компилятор проверяет, существует ли элемент кода, и приводит `member` к каноническому имени элемента в выходных XML-данных. *member* необходимо заключать в двойные кавычки (" ").

  Сведения о создании ссылки cref на универсальный тип см. в статье об [атрибуте cref](./cref-attribute.md).

- `description`

  Описание уровня доступа для члена.

## <a name="remarks"></a>Примечания

Тег `<permission>` позволяет документировать уровень доступа для элемента. Задать уровень доступа для члена можно с помощью класса <xref:System.Security.PermissionSet>.

Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).

## <a name="example"></a>Пример

[!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
