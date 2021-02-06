---
description: Дополнительные сведения <summary> (Visual Basic)
title: <summary>
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 4d4b1ecf0fa054eb625c1a3cf09c1cab4e661ef2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640294"
---
# <a name="summary-visual-basic"></a>\<summary> (Visual Basic)

Указывает сводку элемента.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a>Параметры  

 `description`  
 Сводка объекта.  
  
## <a name="remarks"></a>Примечания  

 Используйте `<summary>` тег для описания типа или члена типа. Чтобы добавить дополнительную информацию в описание типа, используйте [\<remarks>](remarks.md).  
  
 Текст для `<summary>` тега — единственный источник сведений о типе в IntelliSense, который также отображается в обозревателе объектов. Дополнительные сведения об обозревателе объектов см. [в разделе Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  

 В этом примере используется `<summary>` тег для описания `ResetCounter` метода и `Counter` Свойства.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](index.md)
