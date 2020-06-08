---
title: -nostdlib
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 0934799853323110e73087ba6d8975c30f84d8f7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387716"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)
Указывает компилятору не ссылаться автоматически на стандартные библиотеки.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр `-nostdlib` удаляет автоматическую ссылку на сборку System.dll и запрещает компилятору считывать файл Vbc.rsp. Файл Vbc.rsp, расположенный в том же каталоге, что и файл Vbc.exe, ссылается на часто используемые сборки .NET Framework и импортирует пространства имен `System` и `Microsoft.VisualBasic`.  
  
> [!NOTE]
> При этом компилятор всегда ссылается на сборки Mscorlib.dll и Microsoft.VisualBasic.dll.  
  
> [!NOTE]
> Параметр `-nostdlib` недоступен в среде разработки Visual Studio. Он доступен только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` без создания ссылок на стандартные библиотеки. Необходимо присвоить константе условной компиляции `_MYTYPE` строку Empty, чтобы удалить объект `My`.  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>См. также

- [-noconfig](noconfig.md)
- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
- [Настройка доступа к объектам через My](../../developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
