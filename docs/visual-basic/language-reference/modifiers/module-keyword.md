---
title: Модуль<keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: 0cb009c22dada7b92956e113d33505923a92f2b3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362428"
---
# <a name="module-keyword-visual-basic"></a>Module \<keyword> (Visual Basic)
Указывает, что атрибут в начале исходного файла применяется к текущему модулю сборки.  
  
## <a name="remarks"></a>Комментарии  
 Многие атрибуты относятся к отдельному программному элементу, например классу или свойству. Вы применяете такой атрибут, присоединив блок атрибута в угловых скобках ( `< >` ) непосредственно к оператору объявления.  
  
 Если атрибут относится не только к следующему элементу, но и к текущему модулю сборки, блок атрибута помещается в начало исходного файла и определяется атрибутом с `Module` ключевым словом. Если он применяется ко всей сборке, используется ключевое слово [Assembly](assembly.md) .  
  
 `Module`Модификатор не совпадает с [оператором module](../statements/module-statement.md).  
  
## <a name="see-also"></a>См. также раздел

- [Сборка](assembly.md)
- [Оператор Module](../statements/module-statement.md)
- [Обзор атрибутов](../../programming-guide/concepts/attributes/index.md)
