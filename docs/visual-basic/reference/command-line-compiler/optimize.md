---
description: 'Дополнительные сведения: -optimize'
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: 812eaa544dd874fd3871e58f366a34ee8176273a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100426703"
---
# <a name="-optimize"></a>-optimize

Разрешает или запрещает оптимизацию компилятора.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`+` &#124; `-`|Необязательный элемент. Параметр `-optimize-` запрещает оптимизацию компилятора. Параметр `-optimize+` разрешает оптимизацию компилятора. По умолчанию оптимизация отключена.|  
  
## <a name="remarks"></a>Примечания  

 Оптимизации компилятора делают код более быстрым, коротким и эффективным. Но поскольку оптимизация изменяет порядок строк кода в файле вывода, `-optimize+` может осложнить процесс отладки.  
  
 Все модули, созданные с помощью `-target:module` для сборки, должны использовать те же параметры `-optimize`, что и сборка. Дополнительные сведения см. в разделе [-target (Visual Basic)](target.md).  
  
 Параметры `-optimize` и `-debug` можно объединить.  
  
|Задание параметра -optimize в интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.<br />     <br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно** .<br />4.  Установите флажок **Включить оптимизацию**.|  
  
## <a name="example"></a>Пример  

 Следующий код компилирует `T2.vb` и включает оптимизацию компилятора.  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [-debug (Visual Basic)](debug.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
- [-target (Visual Basic)](target.md)
