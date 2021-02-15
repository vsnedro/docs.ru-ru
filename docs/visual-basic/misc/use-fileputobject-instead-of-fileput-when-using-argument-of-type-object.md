---
description: 'Дополнительные сведения: используйте "FilePutObject" вместо "FilePut" при использовании аргумента типа "Object"'
title: При использовании аргумента с типом Object применяйте FilePutObject вместо FilePut
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: 5e5822999aa39bff4d43f83a2719341034cdcadc
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100460102"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a>При использовании аргумента с типом Object применяйте FilePutObject вместо FilePut

Метод `FilePut` включает аргумент типа `Object`. Чтобы избежать неоднозначности, следует использовать`FilePutObject` вместо `FilePut` .  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Замените `FilePut` на `FilePutObject`.  
  
- Приведите аргумент `Object` к более конкретному типу.  
  
- Используйте функциональность объекта `My.Computer.FileSystem` .  
  
## <a name="see-also"></a>См. также раздел

- [My. Computer. FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [My. Computer. FileSystem. WriteAllBytes](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
