---
title: <list>
ms.date: 07/20/2015
helpviewer_keywords:
- listheader XML tag
- <item> XML tag
- <list> XML tag
- <listheader> XML tag
- term XML tag
- list XML tag
- <description> XML tag
- description XML tag
- item XML tag
- <term> XML tag
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
ms.openlocfilehash: 900cd8c467a21812d980cffa7e41120ae557704b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872787"
---
# <a name="list-visual-basic"></a>\<list> (Visual Basic)

Определяет список или таблицу.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<list type="type">  
   <listheader>  
      <term>term</term>  
      <description>description</description>  
   </listheader>  
   <item>  
      <term>term</term>  
      <description>description</description>  
   </item>  
</list>  
```  
  
## <a name="parameters"></a>Параметры  

 `type`  
 Тип списка. Должен быть "маркированным" для маркированного списка, "число" для нумерованного списка или "Таблица" для таблицы из двух столбцов.  
  
 `term`  
 Используется, только если `type` имеет значение "Table". Термин для определения, который определен в теге description.  
  
 `description`  
 Если параметр `type` имеет значение "маркированный" или "Number", `description` то элемент списка, если `type` "Table", `description` является определением `term` .  
  
## <a name="remarks"></a>Примечания  

 `<listheader>`Блок определяет заголовок таблицы или списка определений. При определении таблицы необходимо указать `term` в заголовке только запись.  
  
 Каждый элемент в списке указывается в блоке `<item>`. При создании списка определений необходимо указать `term` и `description` . Однако для таблицы, маркированного списка или нумерованного списка необходимо указать только запись для `description` .  
  
 Число блоков `<item>` в списке или таблице не ограничено.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  

 В этом примере `<list>` тег используется для определения маркированного списка в разделе "Примечания".  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](index.md)
