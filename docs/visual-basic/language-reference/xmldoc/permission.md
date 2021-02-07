---
description: Дополнительные сведения <permission> (Visual Basic)
title: <permission>
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 7a227e97051002c834c96297d3028f08e3ed07ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700264"
---
# <a name="permission-visual-basic"></a>\<permission> (Visual Basic)

Указывает требуемое разрешение для элемента.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a>Параметры  

 `member`  
 Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции. Компилятор проверяет, существует ли элемент кода, и приводит `member` к каноническому имени элемента в выходных XML-данных. Заключите `member` в кавычки ("").  
  
 `description`  
 Описание уровня доступа для члена.  
  
## <a name="remarks"></a>Примечания  

 Используйте `<permission>` тег для документирования доступа к элементу. Используйте <xref:System.Security.PermissionSet> класс, чтобы указать доступ к элементу.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  

 В этом примере `<permission>` тег используется для описания того, что объект <xref:System.Security.Permissions.FileIOPermission> является обязательным для `ReadFile` метода.  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](index.md)
