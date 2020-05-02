---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: c57ed1699d110959e9faf3dc3d43bcc200851c1c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005432"
---
# <a name="-noconfig"></a>-noconfig
Указывает, что компилятор не должен автоматически ссылаться на часто используемые сборки .NET Framework и импортировать пространства имен `System` и `Microsoft.VisualBasic`.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр `-noconfig` указывает компилятору не выполнять сборку с использованием файла Vbc.rsp, который располагается в том же каталоге, что и файл Vbc.exe. Файл Vbc.rsp ссылается на часто используемые сборки .NET Framework и импортирует пространства имен `System` и `Microsoft.VisualBasic`. Компилятор неявно ссылается на сборку System.dll, если не указан параметр `-nostdlib`. Параметр `-nostdlib` указывает компилятору не выполнять сборку с использованием файла Vbc.rsp и не ссылаться на сборку System.dll автоматически.  
  
> [!NOTE]
> При этом компилятор всегда ссылается на сборки Mscorlib.dll и Microsoft.VisualBasic.dll.  
  
 Можно изменить файл Vbc.rsp, указав дополнительные параметры компилятора, которые должны включаться в каждую компиляцию Vbc.exe (за исключением случаев, когда указан параметр `-noconfig`). Дополнительные сведения см. в документации синтаксиса [@ (указание файла ответа)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).  
  
 Компилятор обрабатывает параметры, передаваемые в команду `vbc`, последними. Таким образом, любой параметр командной строки переопределяет значение аналогичного параметра в файле Vbc.rsp.  
  
> [!NOTE]
> Параметр `-noconfig` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также

- [-nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [@ (указание файла ответов)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
