---
title: <paramref>
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: d7aacc5faea22f9c5a4b865a32c832154fe624c5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872610"
---
# <a name="paramref-visual-basic"></a>\<paramref> (Visual Basic)

Форматирует слово как параметр.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a>Параметры  

 `name`  
 Имя параметра, на который указывается ссылка. Имя заключается в двойные кавычки (" ").  
  
## <a name="remarks"></a>Примечания  

 `<paramref>`Тег дает возможность указать, что слово является параметром. XML-файл может быть обработан для того, чтобы отформатировать этот параметр определенным образом.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  

 В этом примере `<paramref>` тег используется для ссылки на `id` параметр.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](index.md)
