---
title: XML-литерал CDATA
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 4447ad6cf0fb251b0d2d1387c109b06d32f69cb8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866101"
---
# <a name="xml-cdata-literal-visual-basic"></a>Литеральное представление XML-раздела CDATA (Visual Basic)

Литерал, представляющий <xref:System.Xml.Linq.XCData> объект.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>Компоненты  

 `<![CDATA[`  
 Обязательный элемент. Обозначает начало раздела XML CDATA.  
  
 `content`  
 Обязательный элемент. Текстовое содержимое, отображаемое в разделе CDATA XML.  
  
 `]]>`  
 Обязательный элемент. Обозначает конец раздела.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Объект <xref:System.Xml.Linq.XCData>.  
  
## <a name="remarks"></a>Remarks  

 Разделы XML CDATA содержат необработанный текст, который должен быть добавлен, но не проанализирован, с XML-кодом, содержащим его. Раздел CDATA XML может содержать любой текст. Сюда входят зарезервированные символы XML. Раздел CDATA XML заканчивается последовательностью "]] >". Это подразумевает следующие моменты:  
  
- Нельзя использовать внедренное выражение в XML-литерале CDATA, так как разделители внедренных выражений являются допустимыми содержимым XML CDATA.  
  
- Разделы CDATA XML не могут быть вложенными, поскольку `content` не могут содержать значение "]] >".  
  
 Можно назначить литерал XML CDATA переменной или включить его в литерал XML-элемента.  
  
> [!NOTE]
> XML-литерал может охватывать несколько строк, но не использует символы продолжения строки. Это позволяет копировать содержимое из XML-документа и вставлять его непосредственно в Visual Basic программу.  
  
 Компилятор Visual Basic преобразует литерал CDATA XML в вызов <xref:System.Xml.Linq.XCData.%23ctor%2A> конструктора.  
  
## <a name="example"></a>Пример  

 В следующем примере создается раздел CDATA, содержащий текст "может содержать литеральные \<XML> теги".  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XCData>
- [XML-литерал элемента](xml-element-literal.md)
- [XML-литералы](index.md)
- [Создание XML в Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
