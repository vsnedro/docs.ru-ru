---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: d058663213cf02f2142bff740aeec1b60791362c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873032"
---
# <a name="code-visual-basic"></a>\<code> (Visual Basic)

Указывает, что текст представляет собой несколько строк кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a>Параметры  

 `content`  
 Текст, помечающий как код.  
  
## <a name="remarks"></a>Примечания  

 Используйте `<code>` тег, чтобы указать несколько строк в виде кода. Используйте, [\<c>](c.md) чтобы указать, что текст в описании должен быть помечен как код.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  

 В этом примере \<code> тег используется для включения примера кода для использования `ID` поля.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](index.md)
