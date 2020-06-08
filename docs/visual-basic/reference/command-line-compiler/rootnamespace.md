---
title: -rootnamespace
ms.date: 03/13/2018
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
ms.openlocfilehash: b6a2f3ba0772d8f8c8c6a762a1be01703d21b778
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403139"
---
# <a name="-rootnamespace"></a>-rootnamespace
Задает пространство имен для всех объявлений типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`namespace`|Имя пространства имен, в котором должны быть заключены все объявления типов для текущего проекта.|  
  
## <a name="remarks"></a>Примечания  
 Если вы используете исполняемый файл Visual Studio (Devenv.exe) для компиляции проекта, созданного в интегрированной среде разработки Visual Studio, используйте `-rootnamespace`, чтобы указать значение свойства <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>. Дополнительные сведения см. в разделе [Параметры командной строки для команды Devenv](/visualstudio/ide/reference/devenv-command-line-switches).  
  
 Используйте дизассемблер MSIL среды CLR (`Ildasm.exe`) для просмотра имен пространств имен в выходном файле.  
  
|Задание параметра -rootnamespace в интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Перейдите на вкладку **Приложение** .<br />3.  Измените значение в поле **Корневое пространство имен**.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и заключает все объявления типов в пространство имен `mynamespace`.  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Ildasm.exe (дизассемблер IL)](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
