---
title: <see>
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 51eaaef2ddb88afbb52ab58b85ed1a58ba251c1e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866448"
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
