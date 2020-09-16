---
title: Схем конфигурации WCF
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: 160be2ea43d1530cdb2ccd3de1f9e6a2e4d0aca3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536396"
---
# <a name="wcf-configuration-schema"></a>Схем конфигурации WCF
Элементы конфигурации Windows Communication Foundation (WCF) позволяют настроить службу WCF и клиентские приложения. [Средство редактирования конфигурации (SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md) можно использовать для создания и изменения файлов конфигурации для клиентов и служб. Поскольку файлы конфигурации имеют формат XML, для их изменения вручную с помощью текстового редактора необходимо уметь работать с XML-кодом. В противном случае возможно возникновение проблем, таких как отсутствие тега или атрибута элемента XML. Это обусловлено тем, что в тегах и атрибутах элементов XML учитывается регистр символов.  
  
 Система конфигурации WCF основана на <xref:System.Configuration> пространстве имен. Поэтому можно использовать все стандартные возможности, имеющиеся в пространстве имен <xref:System.Configuration>, например блокировку, шифрование и объединение конфигурации для повышения безопасности приложения и его конфигурации. Дополнительные сведения об этих возможностях см. в следующих разделах:  
  
 [Шифрование данных конфигурации](/previous-versions/aspnet/53tyfkaw(v=vs.100))  
  
 [Блокировка параметров конфигурации](/previous-versions/aspnet/55th21y4(v=vs.100))  
  
 В этом разделе описаны все возможные значения каждого элемента конфигурации и их взаимодействие с другими элементами конфигурации WCF. Следующая схема иллюстрирует схему конфигурации WCF:  
  
 ![Схема, на которой показана схема конфигурации WCF.](./media/index/windows-communication-foundation-configuration-schema.gif)  
  
> [!CAUTION]
> Разделы конфигурации WCF следует защищать в файлах конфигурации приложения (app.config) с соответствующими списками управления доступом (ACL), чтобы предотвратить потенциальные угрозы безопасности.  Например, необходимо гарантировать, что иметь доступ или изменять параметры безопасности в привязках приложения или разделе модели службы в файле конфигурации для службы смогут только определенные лица.  
  
## <a name="in-this-section"></a>в этом разделе  
 [\<system.serviceModel>](system-servicemodel.md)  
 Приводится описание элемента `ServiceModel`.  
  
 [\<system.serviceModel.activation>](system-servicemodel-activation.md)  
 Настраивает средство SMSvcHost.exe.  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
 Элемент верхнего уровня для установки параметров при использовании сериализаторов, таких как <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Configuring Windows Communication Foundation Applications](../../../wcf/configuring-services.md)  
 Описывает настройку служб и клиентов WCF.
