---
title: Слишком много файлов
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: cd168ce86569d2d7558e21a5b4cc5ef385b28313
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873545"
---
# <a name="too-many-files"></a>Слишком много файлов

В корневом каталоге создано либо больше файлов, чем разрешено операционной системой, либо открыто более файлов, чем указано в параметре **Files =** в файле CONFIG.SYS.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Если программа открывает, закрывает или сохраняет файлы в корневом каталоге, измените программу так, чтобы она использовала подкаталог.  
  
2. Увеличьте число файлов, указанных в параметре **Files** , в файле CONFIG.SYS и перезагрузите компьютер.  
  
## <a name="see-also"></a>См. также

- [Типы ошибок](../../programming-guide/language-features/error-types.md)
