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
ms.openlocfilehash: 955c1a4c5c5619f908b8d03dbf12360c23574478
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400090"
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
  
## <a name="remarks"></a>Комментарии  
 `<listheader>`Блок определяет заголовок таблицы или списка определений. При определении таблицы необходимо указать `term` в заголовке только запись.  
  
 Каждый элемент в списке указывается `<item>` блоком. При создании списка определений необходимо указать `term` и `description` . Однако для таблицы, маркированного списка или нумерованного списка необходимо указать только запись для `description` .  
  
 Список или таблица может содержать столько `<item>` блоков, сколько необходимо.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере `<list>` тег используется для определения маркированного списка в разделе "Примечания".  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>См. также раздел

- [XML-теги для комментариев](index.md)
