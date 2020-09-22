---
title: <exception>
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: e3f386d2a1e15ea3e1519d6e1e5e31c34c73fb99
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872894"
---
# <a name="exception-visual-basic"></a>\<exception> (Visual Basic)

Указывает, какие исключения могут быть созданы.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a>Параметры  

 `member`  
 Ссылка на исключение, которое доступно из текущей среды компиляции. Компилятор проверяет, существует ли исключение, и приводит `member` к каноническому имени элемента в выходных XML-данных. `member` необходимо заключать в двойные кавычки (" ").  
  
 `description`  
 Описание.  
  
## <a name="remarks"></a>Remarks  

 Используйте `<exception>` тег, чтобы указать, какие исключения могут быть созданы. Этот тег применяется к определению метода.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  

 В этом примере `<exception>` тег используется для описания исключения, которое `IntDivide` может выдаваться функцией.  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](index.md)
