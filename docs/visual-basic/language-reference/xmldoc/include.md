---
title: <include>
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 78a10624107cea349b01f484c641190a945dbd7e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400115"
---
# <a name="include-visual-basic"></a>\<include> (Visual Basic)
Ссылается на другой файл, описывающий типы и члены в исходном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a>Параметры  
 `filename`  
 Обязательный. Имя файла, содержащего документацию. Имя файла может быть дополнено с указанием пути. Заключите `filename` в двойные кавычки ("").  
  
 `tagpath`  
 Обязательный. Путь тегов в `filename`, который ведет к тегу `name`. Заключите путь в двойные кавычки ("").  
  
 `name`  
 Обязательный. Описатель имени в теге, который предшествует комментариям. `Name`будет иметь `id` .  
  
 `id`  
 Обязательный. Идентификатор тега, который предшествует комментариям. Заключите идентификатор в одинарные кавычки (' ').  
  
## <a name="remarks"></a>Комментарии  
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
  
## <a name="see-also"></a>См. также раздел

- [XML-теги для комментариев](index.md)
