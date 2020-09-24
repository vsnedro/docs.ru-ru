---
title: <serviceSecurityAudit>
ms.date: 03/30/2017
ms.assetid: ba517369-a034-4f8e-a2c4-66517716062b
ms.openlocfilehash: 6cec3373dae3127f16bb8a418a91a684554f2b0c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153668"
---
# \<serviceSecurityAudit>

Задает параметры, позволяющие проводить аудит событий безопасности во время обслуживания.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceSecurityAudit>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<serviceSecurityAudit auditLogLocation="Default/Application/Security"
                      messageAuthenticationAuditLevel="None/Success/Failure/SuccessOrFailure"
                      serviceAuthorizationAuditLevel="None/Success/Failure/SuccessOrFailure"
                      suppressAuditFailure="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|auditLogLocation|Задает местоположение журнала аудита. Допустимые значения.<br /><br /> — По умолчанию: события безопасности записываются в журнал приложений в Windows XP, а также в журнал событий в Windows Server 2003 и Windows Vista.<br />-Application: события аудита записываются в журнал событий приложений.<br />-Security: события аудита записываются в журнал событий безопасности.<br /><br /> Значение по умолчанию — Default. Для получения дополнительной информации см. <xref:System.ServiceModel.AuditLogLocation>.|  
|suppressAuditFailure|Логическое значение, задающее поведение для подавления ошибок записи в журнал аудита.<br /><br /> Приложения должны уведомляться об ошибках записи в журнал аудита. Если в приложении не предусмотрена обработка ошибок аудита, необходимо использовать этот атрибут для подавления ошибок записи в журнал аудита.<br /><br /> Если этот атрибут имеет значение `true`, исключения, кроме OutOfMemoryException, StackOverFlowException, ThreadAbortException и ArgumentException, которые являются результатом попыток записи событий аудита, обрабатываются системой и не распространяются на приложение. Если значением этого атрибута является `false`, все исключения, которые являются результатом попыток записи событий аудита, пропускаются в приложение.<br /><br /> Значение по умолчанию — `true`.|  
|serviceAuthorizationAuditLevel|Задает типы событий авторизации, записываемых в журнал аудита. Допустимые значения.<br /><br /> -None: аудит событий авторизации службы не выполняется.<br />— Успешно. аудит выполняется только для успешных событий авторизации службы.<br />-Failure: аудит только событий авторизации службы не выполняется.<br />-Сукцессорфаилуре. аудит успешных и неудачных событий авторизации службы.<br /><br /> По умолчанию используется None. Для получения дополнительной информации см. <xref:System.ServiceModel.AuditLevel>.|  
|messageAuthenticationAuditLevel|Задает тип событий аудита проверки подлинности сообщений, заносимых в журнал. Допустимые значения.<br /><br /> -None: события аудита не создаются.<br />— Успешное выполнение. регистрируются только события безопасности (полная проверка, включая проверку подписи сообщения, шифрование и проверка маркера).<br />-Failure: регистрируются только события сбоя.<br />-Сукцессорфаилуре. регистрируются события успешного и неуспешного выполнения.<br /><br /> По умолчанию используется None. Для получения дополнительной информации см. <xref:System.ServiceModel.AuditLevel>.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Указывает элемент поведения.|  
  
## <a name="remarks"></a>Remarks  

 Этот элемент конфигурации используется для аудита событий проверки подлинности Windows Communication Foundation (WCF). При включенном аудите может выполняться аудит либо успешных, либо неудачных попыток проверки подлинности (или попыток обоих видов). События записываются в один из трех журналов событий: журнал приложения, журнал безопасности или журнал, используемый по умолчанию в данной версии операционной системы. Все журналы событий можно просматривать при помощи средства просмотра событий Windows.  
  
 Подробный пример использования этого элемента конфигурации см. в разделе [поведение аудита служб](../../../wcf/samples/service-auditing-behavior.md).  
  
 По умолчанию в Windows XP события аудита отображаются в журнале приложений, а в операционных системах Windows Server 2003 и Windows Vista события аудита можно просмотреть в журнале безопасности. Местоположение событий аудита можно задать, присвоив атрибуту `auditLogLocation` значение "Application" или "Security". Дополнительные сведения см. [в разделе инструкции. Аудит событий безопасности](../../../wcf/feature-details/how-to-audit-wcf-security-events.md). Если события записываются в журнал безопасности, то параметру Локалсекуритиполици-> включить доступ к объекту следует задать для параметра "успех" и "сбой".  
  
 При просмотре журнала событий источником событий аудита является "ServiceModel Audit 3.0.0.0". Записи аудита проверки подлинности сообщений относятся к категории "MessageAuthentication", а записи аудита авторизации служб - к категории "ServiceAuthorization".  
  
 События аудита проверки подлинности сообщений указывают, не было ли сообщение подделано, не истек ли срок сообщения, а также может ли клиент пройти проверку подлинности при подключении к службе. Они предоставляют следующие сведения: результат проверки подлинности, идентификационные данные клиента и конечной точки, в которую было отправлено сообщение, а также действие, связанное с сообщением.  
  
 К событиям аудита авторизации службы относится решение об авторизации, принятое диспетчером авторизации служб. Они предоставляют сведения о том, завершилась ли авторизация успешно или неудачно с удостоверением клиента, конечной точкой, куда было отправлено сообщение, действием, связанным с сообщением, идентификатором контекста авторизации, который был создан во входящем сообщении, и типом диспетчера авторизации, который выполнил решение о доступе.  
  
## <a name="example"></a>Пример  
  
```xml  
<system.serviceModel>
  <behaviors>
    <serviceBehaviors>
      <behavior name="NewBehavior">
        <serviceSecurityAudit auditLogLocation="Application"
                              suppressAuditFailure="true"
                              serviceAuthorizationAuditLevel="Success"
                              messageAuthenticationAuditLevel="Success" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.Configuration.ServiceSecurityAuditElement>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- [Поведение безопасности](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Аудит](../../../wcf/feature-details/auditing-security-events.md)
- [Практическое руководство. Аудит событий безопасности](../../../wcf/feature-details/how-to-audit-wcf-security-events.md)
- [Поведение аудита службы](../../../wcf/samples/service-auditing-behavior.md)
