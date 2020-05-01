---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 6b4b69d227c857442de6857fac023090b3698e81
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004644"
---
# <a name="-win32icon"></a>-win32icon
Внедряет ICO-файл в выходной файл. Этот ICO-файл представляет выходной файл в **проводнике**.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`filename`|ICO-файл, который требуется добавить в выходной файл. Если имя файла содержит пробел, заключите это имя в кавычки (" ").|  
  
## <a name="remarks"></a>Примечания  
 Вы можете создать ICO-файл с помощью компилятора ресурсов Microsoft Windows (RC). Компилятор ресурсов вызывается при компиляции программы Visual C++. При этом ICO-файл создается из RC-файла. Параметры `-win32icon` и `-win32resource` являются взаимоисключающими.  
  
 Чтобы создать ссылку на файл ресурсов .NET Framework, см. раздел [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md). Чтобы присоединить файл ресурсов .NET, см. раздел [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md). См. сведения об импорте RES-файла в разделе [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md).  
  
|Чтобы задать параметр -win32icon в Visual Studio IDE, сделайте следующее:|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Перейдите на вкладку **Приложение** .<br />3.  Измените значение в поле **Значок**.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и присоединяет ICO-файл `Rf.ico`.  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
