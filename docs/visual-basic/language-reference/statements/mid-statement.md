---
title: Оператор Mid
ms.date: 07/20/2015
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
ms.openlocfilehash: 90408fd8a8cfc9b74c8422d0571d61f8534403f3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404459"
---
# <a name="mid-statement"></a>Оператор Mid
Заменяет указанное число символов в `String` переменной символами из другой строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a>Компоненты  
 `Target`  
 Обязательный. Имя переменной, `String` которую необходимо изменить.  
  
 `Start`  
 Обязательный. Выражение `Integer`. Место в символах `Target` , с которого начинается замена текста. `Start`использует индекс, отсчитываемый от единицы.  
  
 `Length`  
 Необязательный элемент. Выражение `Integer`. Число символов для замены. Если этот параметр опущен, `String` используются все.  
  
 `StringExpression`  
 Обязательный. `String`выражение, которое заменяет часть `Target` .  
  
## <a name="exceptions"></a>Исключения  
  
|Тип исключения|Условие|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start`<= 0 или `Length` < 0.|  
  
## <a name="remarks"></a>Комментарии  
 Число заменяемых символов всегда меньше или равно числу символов в `Target` .  
  
 Visual Basic содержит <xref:Microsoft.VisualBasic.Strings.Mid%2A> функцию и `Mid` оператор. Эти элементы работают с указанным числом символов в строке, но `Mid` функция возвращает символы, пока `Mid` оператор заменяет символы. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
> `MidB`Инструкция более ранних версий Visual Basic заменяет подстроку в байтах, а не на символы. Он используется в основном для преобразования строк в приложениях с двухбайтовой кодировкой (DBCS). Все строки Visual Basic в Юникоде и больше не `MidB` поддерживаются.  
  
## <a name="example"></a>Пример  
 В этом примере используется `Mid` оператор для замены указанного числа символов в строковой переменной символами из другой строки.  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [Microsoft. VisualBasic](../runtime-library-members.md)  
  
 **Модуль:**`Strings`  
  
 **Сборка:** Библиотека времени выполнения Visual Basic (в Microsoft. VisualBasic. dll)  
  
## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [Строки](../../programming-guide/language-features/strings/index.md)
- [Знакомство со строками в Visual Basic](../../programming-guide/language-features/strings/introduction-to-strings.md)
