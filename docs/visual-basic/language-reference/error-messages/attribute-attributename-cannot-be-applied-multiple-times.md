---
title: Атрибут <attributename> не может применяться многократно
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 27cbe6d0043179c4a5d52baae06bad805f9d1d3a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162665"
---
# <a name="bc30663-attribute-attributename-cannot-be-applied-multiple-times"></a>BC30663: атрибут " \<attributename> " не может применяться несколько раз

Атрибут можно применить только один раз. `AttributeUsage`Атрибут определяет, можно ли применить атрибут более одного раза.

 **Идентификатор ошибки:** BC30663

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Убедитесь, что атрибут применяется только один раз.

2. Если вы используете созданные вами настраиваемые атрибуты, попробуйте изменить их `AttributeUsage` атрибут, чтобы разрешить использование нескольких атрибутов, как показано в следующем примере.

```vb
<AttributeUsage(AllowMultiple := True)>
```

## <a name="see-also"></a>См. также

- <xref:System.AttributeUsageAttribute>
- [Создание настраиваемых атрибутов](../../programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../programming-guide/concepts/attributes/attributeusage.md)
