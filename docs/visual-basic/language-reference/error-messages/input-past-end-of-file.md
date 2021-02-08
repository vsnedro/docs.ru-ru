---
description: 'Дополнительные сведения о: ввод за концом файла'
title: Оператор Input обнаружил конец файла
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: b65a57bdc56367518a93880be28781e56c9b99cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796045"
---
# <a name="input-past-end-of-file"></a>Оператор Input обнаружил конец файла

Либо `Input` инструкция считывает из файла, который является пустым, либо в котором используются все данные, либо вы использовали `EOF` функцию с файлом, открытым для двоичного доступа.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Используйте `EOF` функцию непосредственно перед `Input` оператором, чтобы определить конец файла.  
  
2. Если файл открыт для двоичного доступа, используйте `Seek` и `Loc` .  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
