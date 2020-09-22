---
title: <include>
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: df8749ca9d6c92cf9ef95f03eea2704812ff495a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872876"
---
# <a name="include-visual-basic"></a>\<include> (Visual Basic)

Ссылается на другой файл, описывающий типы и члены в исходном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a>Параметры  

 `filename`  
 Обязательный элемент. Имя файла, содержащего документацию. Имя файла может быть дополнено с указанием пути. Заключите `filename` в двойные кавычки ("").  
  
 `tagpath`  
 Обязательный элемент. Путь тегов в `filename`, который ведет к тегу `name`. Заключите путь в двойные кавычки ("").  
  
 `name`  
 Обязательный элемент. Описатель имени в теге, который предшествует комментариям. `Name` будет иметь `id` .  
  
 `id`  
 Обязательный элемент. Идентификатор тега, который предшествует комментариям. Заключите идентификатор в одинарные кавычки (' ').  
  
## <a name="remarks"></a>Remarks  

 Используйте `<include>` тег для ссылки на комментарии в другом файле, описывающем типы и члены в исходном коде. Этот способ является альтернативой размещению комментариев документации непосредственно в файле исходного кода.  
  
 `<include>`Тег использует рекомендацию W3C по языку XML Path (XPath) версии 1,0. Дополнительные сведения о способах настройки `<include>` использования см. в разделе <https://www.w3.org/TR/xpath> .  
  
## <a name="example"></a>Пример  

 В этом примере `<include>` тег используется для импорта комментариев документации элемента из файла с именем `commentFile.xml` .  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 Формат `commentFile.xml` имеет следующий вид.  
  
```xml  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](index.md)
