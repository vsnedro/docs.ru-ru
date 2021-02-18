---
description: 'Дополнительные сведения: -removeintchecks'
title: -removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
ms.openlocfilehash: 1dc484e1538718b68fe9f0cc450fa2480dc52412
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474100"
---
# <a name="-removeintchecks"></a>-removeintchecks

Включает и отключает проверку условий переполнения для целочисленных операций.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`+` &#124; `-`|Необязательный элемент. Если задан параметр `-removeintchecks-`, компилятор проверяет условия переполнения всех целочисленных операций. Значение по умолчанию — `-removeintchecks-`.<br /><br /> Если задано `-removeintchecks` или `-removeintchecks+`, переполнение не проверяется и целочисленные вычисления выполняются быстрее. Однако в случае переполнения типа данных при отключенной проверке переполнения могут сохраниться неверные результаты без отображения ошибки.|  
  
|Задание параметра -removeintchecks в интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно** .<br />4.  Установите флажок **Отключить проверку переполнения для целочисленных значений**.|  
  
## <a name="example"></a>Пример  

 Следующий код компилирует `Test.vb` и отключает проверку переполнения целочисленных значений.  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
