---
description: 'Дополнительные сведения: <see> (Visual Basic)'
title: <see>
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 46dd67710f83d6c4549ddfeb6b7bbc1503b7aa1e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640346"
---
# <a name="see-visual-basic"></a>\<see> (Visual Basic)

Указывает ссылку на другой элемент.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a>Параметры  

 `member`  
 Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции. Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных. `member` необходимо заключать в двойные кавычки (" ").  
  
## <a name="remarks"></a>Remarks  

 Используйте `<see>` тег, чтобы указать ссылку в тексте. Используется [\<seealso>](seealso.md) для обозначения текста, который может потребоваться отобразить в разделе "см. также".  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  

 В этом примере используется `<see>` тег в `UpdateRecord` разделе "Примечания" для ссылки на `DoesRecordExist` метод.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](index.md)
