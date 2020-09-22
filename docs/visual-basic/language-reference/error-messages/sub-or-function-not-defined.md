---
title: Подпрограмма или функция не определена
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 24e290ce1193cd6bc6a0ec8985902576332423f2
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870523"
---
# <a name="sub-or-function-not-defined-visual-basic"></a>Sub или Function не определена (Visual Basic)

`Sub` `Function` Для вызова необходимо определить или. Возможные причины этой ошибки:  
  
- Ошибка написания имени процедуры.  
  
- Попытка вызвать процедуру из другого проекта без явного добавления ссылки на этот проект в диалоговом окне " **ссылки** ".  
  
- Указание процедуры, которая не является видимой для вызывающей процедуры.  
  
- Объявление подпрограммы библиотеки динамической компоновки Windows (DLL) или служебной программы-ресурса для Macintosh, которая не находится в указанной библиотеке или ресурсе кода.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Убедитесь, что имя процедуры написано правильно.  
  
2. Найдите имя проекта, содержащего процедуру, которую необходимо вызвать, в диалоговом окне **ссылки** . Если она не отображается, нажмите кнопку **Обзор** , чтобы найти ее. Установите флажок слева от имени проекта и нажмите кнопку **ОК**.  
  
3. Проверьте имя подпрограммы.  
  
## <a name="see-also"></a>См. также

- [Типы ошибок](../../programming-guide/language-features/error-types.md)
- [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)
- [Оператор Sub](../statements/sub-statement.md)
- [Оператор Function](../statements/function-statement.md)
