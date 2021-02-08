---
description: Дополнительные сведения <example> (Visual Basic)
title: <example>
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 643e06fd24e38123dd2693d671b9ab33da5b413e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787491"
---
# <a name="example-visual-basic"></a>\<example> (Visual Basic)

Указывает пример для элемента.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a>Параметры  

 `description`  
 Описание примера кода.  
  
## <a name="remarks"></a>Примечания  

 Тег `<example>` позволяет указать пример использования метода или другого элемента библиотеки. Вместе с ним часто применяется тег [\<code>](code.md).  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  

 В этом примере `<example>` тег используется для включения примера использования `ID` поля.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](index.md)
