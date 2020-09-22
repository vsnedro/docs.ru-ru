---
title: Модуль <keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: 6c4f24ad161302835be683e9d324ce32b16c4087
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867980"
---
# <a name="module-keyword-visual-basic"></a>Module \<keyword> (Visual Basic)

Указывает, что атрибут в начале исходного файла применяется к текущему модулю сборки.  
  
## <a name="remarks"></a>Remarks  

 Многие атрибуты относятся к отдельному программному элементу, например классу или свойству. Вы применяете такой атрибут, присоединив блок атрибута в угловых скобках ( `< >` ) непосредственно к оператору объявления.  
  
 Если атрибут относится не только к следующему элементу, но и к текущему модулю сборки, блок атрибута помещается в начало исходного файла и определяется атрибутом с `Module` ключевым словом. Если он применяется ко всей сборке, используется ключевое слово [Assembly](assembly.md) .  
  
 `Module`Модификатор не совпадает с [оператором module](../statements/module-statement.md).  
  
## <a name="see-also"></a>См. также

- [Сборка](assembly.md)
- [Оператор Module](../statements/module-statement.md)
- [Обзор атрибутов](../../programming-guide/concepts/attributes/index.md)
