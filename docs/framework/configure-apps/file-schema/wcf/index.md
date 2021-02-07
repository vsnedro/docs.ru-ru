---
description: Дополнительные сведения о схеме конфигурации WCF
title: Схем конфигурации WCF
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: 31307fd299cc1e0b63d92b43b33aabafa28858f0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725770"
---
# <a name="wcf-configuration-schema"></a>Схем конфигурации WCF

Элементы конфигурации Windows Communication Foundation (WCF) позволяют настроить службу WCF и клиентские приложения. [Средство редактирования конфигурации (SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md) можно использовать для создания и изменения файлов конфигурации для клиентов и служб. Поскольку файлы конфигурации имеют формат XML, для их изменения вручную с помощью текстового редактора необходимо уметь работать с XML-кодом. В противном случае возможно возникновение проблем, таких как отсутствие тега или атрибута элемента XML. Это обусловлено тем, что в тегах и атрибутах элементов XML учитывается регистр символов.  
  
 Система конфигурации WCF основана на <xref:System.Configuration> пространстве имен. Поэтому можно использовать все стандартные возможности, имеющиеся в пространстве имен <xref:System.Configuration>, например блокировку, шифрование и объединение конфигурации для повышения безопасности приложения и его конфигурации. Дополнительные сведения об этих возможностях см. в следующих разделах:  
  
 [Шифрование данных конфигурации](/previous-versions/aspnet/53tyfkaw(v=vs.100))  
  
 [Блокировка параметров конфигурации](/previous-versions/aspnet/55th21y4(v=vs.100))  
  
 В этом разделе описаны все возможные значения каждого элемента конфигурации и их взаимодействие с другими элементами конфигурации WCF. Следующая схема иллюстрирует схему конфигурации WCF:

:::image type="content" source="./media/index/windows-communication-foundation-configuration-schema.gif" alt-text="Схема, на которой показана схема конфигурации WCF." lightbox="./media/index/windows-communication-foundation-configuration-schema.gif":::
  
> [!CAUTION]
> Защитите разделы конфигурации WCF в файлах конфигурации приложения (app.config) с соответствующими списками управления доступом (ACL), чтобы предотвратить потенциальные угрозы безопасности. Например, убедитесь, что доступ или изменение параметров безопасности для привязок приложений разрешено только соответствующим пользователям, или раздел Service Model файла конфигурации для службы.  
  
## <a name="in-this-section"></a>В этом разделе  

 [\<system.serviceModel>](system-servicemodel.md)  
 Приводится описание элемента `ServiceModel`.  
  
 [\<system.serviceModel.activation>](system-servicemodel-activation.md)  
 Настраивает средство SMSvcHost.exe.  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
 Элемент верхнего уровня для установки параметров при использовании сериализаторов, таких как <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## <a name="related-sections"></a>См. также  

 [Configuring Windows Communication Foundation Applications](../../../wcf/configuring-services.md)  
 Описывает настройку служб и клиентов WCF.
