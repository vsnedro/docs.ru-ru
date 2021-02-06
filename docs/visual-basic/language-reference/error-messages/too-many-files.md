---
description: 'Дополнительные сведения: слишком много файлов'
title: Слишком много файлов
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: 85d246c49f765cf618bf889d75dcc9c10b780280
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641230"
---
# <a name="too-many-files"></a>Слишком много файлов

В корневом каталоге создано либо больше файлов, чем разрешено операционной системой, либо открыто более файлов, чем указано в параметре **Files =** в файле CONFIG.SYS.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Если программа открывает, закрывает или сохраняет файлы в корневом каталоге, измените программу так, чтобы она использовала подкаталог.  
  
2. Увеличьте число файлов, указанных в параметре **Files** , в файле CONFIG.SYS и перезагрузите компьютер.  
  
## <a name="see-also"></a>См. также

- [Типы ошибок](../../programming-guide/language-features/error-types.md)
