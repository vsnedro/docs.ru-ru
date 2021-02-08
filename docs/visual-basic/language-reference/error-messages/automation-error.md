---
description: 'Дополнительные сведения: ошибка службы автоматизации'
title: Ошибка автоматизации
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: e4d283b16b4c54e2488fedfc58d3c881cf6b0218
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797124"
---
# <a name="automation-error"></a>Ошибка автоматизации

При выполнении метода либо при получении либо установке значения свойства переменной объекта возникла ошибка. О ней сообщило приложение, создавшее этот объект.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Проверьте свойства объекта `Err`, чтобы определить причину и характер ошибки.  
  
2. Используйте инструкцию `On Error Resume Next` непосредственно перед инструкцией доступа, а затем выполните проверку на наличие ошибок сразу после инструкции доступа.  
  
## <a name="see-also"></a>См. также

- [Типы ошибок](../../programming-guide/language-features/error-types.md)
- [Обращайтесь к нам](/visualstudio/ide/feedback-options)
