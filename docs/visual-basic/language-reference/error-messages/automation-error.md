---
title: Ошибка автоматизации
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: d62ba57db8bffefb2cfebed705251d87fe285602
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409898"
---
# <a name="automation-error"></a>Ошибка автоматизации

При выполнении метода либо при получении либо установке значения свойства переменной объекта возникла ошибка. О ней сообщило приложение, создавшее этот объект.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Проверьте свойства объекта `Err`, чтобы определить причину и характер ошибки.  
  
2. Используйте инструкцию `On Error Resume Next` непосредственно перед инструкцией доступа, а затем выполните проверку на наличие ошибок сразу после инструкции доступа.  
  
## <a name="see-also"></a>См. также раздел

- [Типы ошибок](../../programming-guide/language-features/error-types.md)
- [Обращайтесь к нам](/visualstudio/ide/feedback-options)
