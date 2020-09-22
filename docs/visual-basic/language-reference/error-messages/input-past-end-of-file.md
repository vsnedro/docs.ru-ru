---
title: Оператор Input обнаружил конец файла
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: c0cb0373fb0652e9600ac8651661708414561aca
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873962"
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
