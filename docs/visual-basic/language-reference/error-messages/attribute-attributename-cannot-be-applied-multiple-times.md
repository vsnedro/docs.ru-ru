---
description: 'Дополнительные сведения о: BC30663: атрибут " <attributename> " не может применяться несколько раз'
title: Атрибут <attributename> не может применяться многократно
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 84b77111a7401eb6f30eb7cd167f4b5689f33e77
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797150"
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
