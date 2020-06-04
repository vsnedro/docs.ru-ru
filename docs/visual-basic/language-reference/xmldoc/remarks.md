---
title: <remarks>
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: c57ddb870192bd94301f99eb71ad29526e8efc28
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400025"
---
# <a name="remarks-visual-basic"></a>\<remarks> (Visual Basic)
Задает раздел примечаний для элемента.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a>Параметры  
 `description`  
 Описание элемента.  
  
## <a name="remarks"></a>Remarks  
 Используйте `<remarks>` тег, чтобы добавить сведения о типе, добавив сведения, указанные в параметре [\<summary>](summary.md) .  
  
 Эти сведения отображаются в обозревателе объектов. Дополнительные сведения об обозревателе объектов см. [в разделе Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере `<remarks>` тег используется для объяснения того, что `UpdateRecord` делает метод.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также раздел

- [XML-теги для комментариев](index.md)
