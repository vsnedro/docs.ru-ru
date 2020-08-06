---
title: Псевдоним extern. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: 891e56b064f8a327abe28293223a85b9d95e8fd3
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301818"
---
# <a name="extern-alias-c-reference"></a>Псевдоним extern (Справочник по C#)
Иногда может потребоваться сослаться на две версии сборок, которые имеют одинаковые полные имена типов. Например, если необходимо использовать две или более версии сборки в одном приложении. Используя внешний псевдоним сборки, пространства имен для каждой сборки можно перенести внутрь пространств имен корневого уровня с именованием по псевдониму, что позволяет использовать их в одном файле.  
  
> [!NOTE]
> Ключевое слово [extern](./extern.md) также используется в качестве модификатора метода, объявляющего метод, написанный в неуправляемом коде.  
  
 Для ссылки на две сборки с одинаковыми полными именами типов псевдоним необходимо указать в командной строке следующим образом:  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 При этом создаются внешние псевдонимы `GridV1` и `GridV2`. Чтобы использовать эти псевдонимы в программе, сошлитесь на них с помощью ключевого слова `extern`. Пример:  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 Каждое объявление псевдонима extern создает дополнительное пространство имен корневого уровня, которое является параллельным для глобального пространства имен (но не находится в его пределах). Таким образом, на типы из каждой сборки можно ссылаться без неоднозначности, используя их полное имя, размещенное в соответствующем пространстве имен-псевдониме.  
  
 В предыдущем примере `GridV1::Grid` является элементом управления сетки из `grid.dll`, а `GridV2::Grid` — элементом управления сетки из `grid20.dll`.  
  
## <a name="using-visual-studio"></a>Использование Visual Studio

Если вы используете Visual Studio, псевдонимы можно указать аналогичным образом.

Добавьте ссылку на *grid.dll* и *grid20.dll* в проект в Visual Studio. Откройте вкладку свойств и измените псевдонимы с глобальных на GridV1 и GridV2 соответственно.

Используйте эти псевдонимы так же, как описано выше.

```csharp
 extern alias GridV1;  
  
 extern alias GridV2;  
```

Теперь можно создать псевдоним для пространства имен или типа, *используя директиву псевдонимов using*. Дополнительные сведения см. в разделе [Директива using](using-directive.md).

```csharp
using Class1V1 = GridV1::Namespace.Class1;

using Class1V2 = GridV2::Namespace.Class1;
```

## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](./index.md)
- [:: Оператор](../operators/namespace-alias-qualifier.md)
- [-reference (параметры компилятора C#)](../compiler-options/reference-compiler-option.md)
