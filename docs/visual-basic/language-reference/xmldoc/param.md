---
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: d325d5f9fbfd132630cf280653be214a267a7a80
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400064"
---
# <a name="param-visual-basic"></a>\<param> (Visual Basic)
Определяет имя и описание параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a>Параметры  
 `name`  
 Имя параметра метода. Имя заключается в двойные кавычки (" ").  
  
 `description`  
 Описание параметра.  
  
## <a name="remarks"></a>Remarks  
 `<param>`Тег должен использоваться в комментариях для объявления метода, чтобы описать один из параметров для метода.  
  
 Текст для `<param>` тега будет отображаться в следующих местах:  
  
- Сведения о параметрах IntelliSense. Дополнительные сведения см. в разделе [Using IntelliSense](/visualstudio/ide/using-intellisense).  
  
- Обозреватель объектов. Дополнительные сведения см. [в разделе Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере `<param>` для описания параметра используется тег `id` .  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также раздел

- [XML-теги для комментариев](index.md)
