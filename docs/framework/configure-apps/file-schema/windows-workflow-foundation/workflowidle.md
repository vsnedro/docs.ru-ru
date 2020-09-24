---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 790e852eb515e19afc324f6e1c25db81ed22999c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148676"
---
# \<workflowIdle>

Поведение службы, управляющее выгрузкой и сохранением простаивающих экземпляров рабочего процесса.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowIdle timeToPersist="TimeSpan"
                    timeToUnload="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|timeToPersist|Значение Timespan, указывающее интервал, который возникает между моментом, когда рабочий процесс становится неактивным, и его сохранением. Значением по умолчанию является TimeSpan.MaxValue.<br /><br /> Начало интервала определяется моментом, когда экземпляр рабочего процесса становится неактивным. Этот атрибут может оказаться полезным в том случае, если необходимо более интенсивно сохранять экземпляр рабочего процесса, оставляя его в памяти как можно дольше. Этот атрибут допустим только в том случае, если его значение меньше, чем атрибут **тиметаунлоад** . Если значение больше, оно не учитывается. Если этот атрибут истекает до значения, заданного атрибутом **тиметаунлоад** , сохраняемость должна завершиться до выгрузки рабочего процесса. Это означает, что операция выгрузки может быть задержана, пока рабочий процесс не будет сохранен. Уровень сохраняемости ответственен за обработку повторений для временных ошибок и выдает исключения только для неустранимых ошибок. В связи с этим все исключения, возникшие во время сохранения, считаются неустранимыми, и производится прерывание работы экземпляра рабочего процесса.|  
|timeToUnload|Значение Timespan, указывающее интервал времени от момента, когда рабочий процесс стал неактивным, до его выгрузки. Значение по умолчанию - 1 минута.<br /><br /> При выгрузке рабочего процесса подразумевается, что было произведено его сохранение. Если этот атрибут имеет нулевое значение, экземпляр рабочего процесса сохраняется и выгружается сразу после того, как становится неактивным. Если задать этому атрибуту значение TimeSpan.MaxValue, операция выгрузки будет фактически отключена. Простаивающие экземпляры рабочего процесса не выгружаются.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<behavior> из \<serviceBehaviors>](behavior-of-servicebehaviors-of-workflow.md)|Указывает элемент поведения.|  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
