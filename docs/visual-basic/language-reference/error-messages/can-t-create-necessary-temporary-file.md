---
title: Не удается создать требуемый временный файл
ms.date: 07/20/2015
f1_keywords:
- vbrID322
ms.assetid: 53617b5b-eb06-4188-b4c2-8607cb9fbc79
ms.openlocfilehash: c6d8e471796a0fb745289df8b3d1b156265949ca
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874663"
---
# <a name="cant-create-necessary-temporary-file"></a>Не удается создать требуемый временный файл

Либо диск заполнен, содержащий каталог, указанный переменной среды TEMP, либо переменная среды TEMP указывает на недопустимый диск или каталог, предназначенный только для чтения.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Удалите файлы с диска, если они заполнены.  
  
2. Укажите другой диск в переменной среды TEMP.  
  
3. Укажите допустимый диск для переменной среды TEMP.  
  
4. Удалите ограничение "только для чтения" из указанного диска или каталога.  
  
## <a name="see-also"></a>См. также

- [Типы ошибок](../../programming-guide/language-features/error-types.md)
