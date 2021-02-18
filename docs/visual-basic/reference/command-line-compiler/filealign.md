---
description: 'Дополнительные сведения: -filealign'
title: -filealign
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
ms.openlocfilehash: f32ae370c0ef832b501f085351eadb9b6156c730
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100470295"
---
# <a name="-filealign"></a>-filealign

Задает выравнивание размеров выходного файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a>Аргументы  

 `number`  
 Обязательный. Значение, которое определяет выравнивание разделов в выходном файле. Допустимые значения: 512, 1024, 2048, 4096 и 8192. Эти значения указаны в байтах.  
  
## <a name="remarks"></a>Примечания  

 Можно использовать параметр `-filealign`, чтобы определить выравнивание разделов в выходном файле. Разделы — это блоки непрерывной памяти в PE-файле, содержащем код или данные. Параметр `-filealign` позволяет компилировать приложение с нестандартным выравниванием. Большинству разработчиков не нужно использовать этот параметр.  
  
 Каждый раздел выравнивается по границе, кратной значению `-filealign`. Фиксированный размер по умолчанию не предусмотрен. Если не указать `-filealign`, компилятор выбирает значение по умолчанию во время компиляции.  
  
 Определив размер раздела, можно изменить размер выходного файла. Изменение размера раздела может применяться для программ, выполняющихся на небольших устройствах.  
  
> [!NOTE]
> Параметр `-filealign` недоступен в среде разработки Visual Studio. Он доступен только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
