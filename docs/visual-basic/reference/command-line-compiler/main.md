---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: fb317b3c555d151e132122c476ce19bdeceb1321
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91065623"
---
# <a name="-main"></a>-main

Задает класс или модуль, содержащий процедуру `Sub Main`.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-main:location  
```  
  
## <a name="arguments"></a>Аргументы  

 `location`  
 Обязательный. Имя класса или модуля, который содержит процедуру `Sub Main` для вызова при запуске программы. Может иметь формат **-main:module** или **-main:namespace.module**.  
  
## <a name="remarks"></a>Примечания  

 Используйте этот параметр при создании исполняемого файла или исполняемой программы Windows. Если параметр **-main** опущен, компилятор ищет допустимый общедоступный объект `Sub Main` во всех открытых классах и модулях.  
  
 Описание разных форм процедуры `Main` см. в статье [о процедуре Main в Visual Basic](../../programming-guide/program-structure/main-procedure.md).  
  
 Если класс `location` наследуется от <xref:System.Windows.Forms.Form>, компилятор предоставляет стандартную процедуру `Main`, которая запускает приложение, если в классе нет процедуры `Main`. Это позволяет компилировать код из командной строки, созданной в среде разработки.  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a>Настройка параметра -main в интегрированной среде разработки Visual Studio  
  
1. Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.  
  
2. Перейдите на вкладку **Приложение** .  
  
3. Снимите флажок **Включить исполняющую среду**.  
  
4. Измените значение в поле **Автоматически запускаемый объект**.  
  
## <a name="example"></a>Пример  

 В следующем код запускается компиляция `T2.vb` и `T3.vb`, а также указано, что процедура `Sub Main` находится в классе `Test2`.  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [-target (Visual Basic)](target.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
- [Процедура Main в Visual Basic](../../programming-guide/program-structure/main-procedure.md)
