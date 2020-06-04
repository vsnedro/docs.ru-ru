---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: c8ba03d9cc01c4751d15c01530c6cbf7d499dc3b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400167"
---
# <a name="c-visual-basic"></a>\<c> (Visual Basic)
Указывает, что текст в описании является кодом.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---|---|  
|`text`|Текст, который нужно указать в качестве кода.|  
  
## <a name="remarks"></a>Комментарии  
 `<c>`Тег дает возможность указать, что текст в описании должен быть помечен как код. Используется [\<code>](code.md) для указания нескольких строк в виде кода.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере `<c>` тег в разделе сводки используется для указания того, что `Counter` является кодом.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>См. также раздел

- [XML-теги для комментариев](index.md)
