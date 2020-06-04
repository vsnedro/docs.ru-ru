---
title: <summary>
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 893ed299b46bd6255ca0e87d008ac53265698614
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411503"
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
  
## <a name="remarks"></a>Remarks  
 Используйте `<summary>` тег для описания типа или члена типа. Используйте [\<remarks>](remarks.md) для добавления дополнительных сведений в описание типа.  
  
 Текст для `<summary>` тега — единственный источник сведений о типе в IntelliSense, который также отображается в обозревателе объектов. Дополнительные сведения об обозревателе объектов см. [в разделе Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<summary>` тег для описания `ResetCounter` метода и `Counter` Свойства.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>См. также раздел

- [XML-теги для комментариев](index.md)
