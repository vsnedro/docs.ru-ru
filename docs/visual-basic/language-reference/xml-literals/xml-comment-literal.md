---
title: XML-литерал комментария
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: 3272cc0f976d6e8819e51bb5d5fce73066007963
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875187"
---
# <a name="xml-comment-literal-visual-basic"></a>XML-литерал комментариев (Visual Basic)

Литерал, представляющий <xref:System.Xml.Linq.XComment> объект.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a>Компоненты  
  
|Термин|Определение|  
|---|---|  
|`<!--`|Обязательный. Обозначает начало XML-комментария.|  
|`content`|Обязательный элемент. Текст, отображаемый в XML-комментарии. Не может содержать последовательность из двух дефисов (--) или заканчиваться дефисом, рядом с закрывающим тегом.|  
|`-->`|Обязательный элемент. Обозначает конец XML-комментария.|  
  
## <a name="return-value"></a>Возвращаемое значение  

 Объект <xref:System.Xml.Linq.XComment>.  
  
## <a name="remarks"></a>Remarks  

 Литералы XML-комментариев не содержат содержимого документа; они содержат сведения о документе. Раздел комментария XML заканчивается последовательностью "-->". Это подразумевает следующие моменты:  
  
- Нельзя использовать внедренное выражение в литерале XML-комментария, так как разделители внедренных выражений являются допустимым содержимым XML-комментариев.  
  
- Разделы комментариев XML не могут быть вложенными, поскольку `content` не могут содержать значение "-->".  
  
 Литерал комментария XML можно назначить переменной или включить в литерал XML-элемента.  
  
> [!NOTE]
> XML-литерал может охватывать несколько строк без использования символов продолжения строки. Эта функция позволяет копировать содержимое из XML-документа и вставлять его непосредственно в Visual Basic программу.  
  
 Компилятор Visual Basic преобразует литерал XML-комментария в вызов <xref:System.Xml.Linq.XComment.%23ctor%2A> конструктора.  
  
## <a name="example"></a>Пример  

 В следующем примере создается XML-комментарий, содержащий текст "это комментарий".  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XComment>
- [XML-литерал элемента](xml-element-literal.md)
- [XML-литералы](index.md)
- [Создание XML в Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
