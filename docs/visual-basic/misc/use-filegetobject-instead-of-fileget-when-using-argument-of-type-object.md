---
description: 'Дополнительные сведения: используйте FileGetObject вместо "FileGet" при использовании аргумента типа "Object"'
title: При использовании аргумента типа Object используйте метод FileGetObject вместо метода FileGet
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 4481fdced961cacf0e652c141601efa13bec776b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471166"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a>При использовании аргумента типа Object используйте метод FileGetObject вместо метода FileGet

Метод `FileGet` включает аргумент типа `Object`. Чтобы избежать неоднозначности, следует использовать`FileGetObject` вместо `FileGet` .  
  
 Обратите внимание, что функциональные возможности, предлагаемые `My.Computer.Filesystem` , проще в использовании и обеспечивают большую производительность, чем `FileGet` или `FileGetObject`.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Замените `FileGet` на `FileGetObject`.  
  
2. Приведите аргумент `Object` к более конкретному типу.  
  
## <a name="see-also"></a>См. также раздел

- [My. Computer. FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
