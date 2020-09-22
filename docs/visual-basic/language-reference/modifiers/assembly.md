---
title: Сборка
ms.date: 07/20/2015
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
ms.openlocfilehash: 34d6b94f31336e3e99b8ca981a9c4899e5a3d912
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875521"
---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)

Указывает, что атрибут в начале исходного файла применяется ко всей сборке.  
  
## <a name="remarks"></a>Remarks  

 Многие атрибуты относятся к отдельному программному элементу, например классу или свойству. Вы применяете такой атрибут, присоединив блок атрибута в угловых скобках ( `< >` ) непосредственно к оператору объявления.  
  
 Если атрибут относится не только к следующему элементу, но и ко всей сборке, блок атрибута помещается в начало исходного файла и определяется атрибутом с `Assembly` ключевым словом. Если он применяется к текущему модулю сборки, используется ключевое слово [module](module-keyword.md) .  
  
 Можно также применить атрибут к сборке в файле AssemblyInfo. vb. в этом случае не нужно использовать блок атрибутов в основном файле исходного кода.  
  
## <a name="see-also"></a>См. также

- [Модуль \<keyword>](module-keyword.md)
- [Обзор атрибутов](../../programming-guide/concepts/attributes/index.md)
