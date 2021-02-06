---
description: Дополнительные сведения см. в статье как заблокировать конечные точки на предприятии.
title: Практическое руководство. Блокировка конечных точек в среде предприятия
ms.date: 03/30/2017
ms.assetid: 1b7eaab7-da60-4cf7-9d6a-ec02709cf75d
ms.openlocfilehash: 8e54c3d1cadcfdb6f0102281813eb3758320a143
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99644233"
---
# <a name="how-to-lock-down-endpoints-in-the-enterprise"></a>Практическое руководство. Блокировка конечных точек в среде предприятия

Крупным предприятиям часто требуется, чтобы приложения разрабатывались в соответствии с политиками безопасности предприятия. В следующем разделе описывается разработка и установка проверяющего элемента управления конечной точки клиента, который может использоваться для проверки всех клиентских приложений Windows Communication Foundation (WCF), установленных на компьютерах.

В этом случае проверяющий элемент управления является проверяющим элементом управления клиента, так как это поведение конечной точки добавляется в [\<commonBehaviors>](../../configure-apps/file-schema/wcf/commonbehaviors.md) раздел клиента в файле machine.config. WCF загружает общие поведения конечной точки только для клиентских приложений и загружает общие поведения службы только для приложений служб. Чтобы установить тот же проверяющий элемент управления для приложения службы, этот элемент управления должен представлять собой поведение службы. Дополнительные сведения см [\<commonBehaviors>](../../configure-apps/file-schema/wcf/commonbehaviors.md) . в разделе.

> [!IMPORTANT]
> Поведения служб или конечных точек, не помеченные <xref:System.Security.AllowPartiallyTrustedCallersAttribute> атрибутом (APTCA), которые добавляются в [\<commonBehaviors>](../../configure-apps/file-schema/wcf/commonbehaviors.md) раздел файла конфигурации, не выполняются, если приложение выполняется в среде с частичным доверием и при этом не возникает исключение. Чтобы принудительно запустить общие поведения, такие как проверяющие элементы управления, необходимо выполнить одно из следующих условий.
>
> - Пометьте общее поведение <xref:System.Security.AllowPartiallyTrustedCallersAttribute> атрибутом, чтобы его можно было запускать при развертывании в качестве приложения с частичным доверием. Обратите внимание, что на компьютере может быть установлен соответствующий параметр реестра, чтобы на нем не могли выполняться сборки, помеченные атрибутом APTCA.
>
> - Убедитесь, что если приложение развертывается как полностью доверенное, пользователи не могут изменять параметры безопасности доступа к коду для запуска приложения в среде с частичным доверием. Если это так, пользовательский проверяющий элемент управления не выполняется и исключение не создается. Чтобы убедиться в этом, ознакомьтесь `levelfinal` с параметром использование [средства политики управления доступом для кода (Caspol.exe)](../../tools/caspol-exe-code-access-security-policy-tool.md).
>
> Дополнительные сведения см. в разделе [рекомендации по частичному доверию](../feature-details/partial-trust-best-practices.md) и [Поддерживаемые сценарии развертывания](../feature-details/supported-deployment-scenarios.md).

### <a name="to-create-the-endpoint-validator"></a>Создание проверяющего элемента конечной точки

1. Создайте расширение <xref:System.ServiceModel.Description.IEndpointBehavior>, в методе <xref:System.ServiceModel.Description.IEndpointBehavior.Validate%2A> которого выполняются необходимые действия по проверке. Пример кода: (Объект `InternetClientValidatorBehavior` берется из примера [проверки безопасности](../samples/security-validation.md) .)

    [!code-csharp[LockdownValidation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorbehavior.cs#2)]

2. Создает новый класс <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, который регистрирует проверяющий элемент управления конечной точки на шаге 1. Это показано в следующем примере кода. (Исходный код для этого примера находится в примере [проверки безопасности](../samples/security-validation.md) .)

    [!code-csharp[LockdownValidation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorelement.cs#3)]

3. Проверьте, что скомпилированная сборка подписана строгим именем. Дополнительные сведения см. в разделе [средство строгих имен (SN.EXE)](../../tools/sn-exe-strong-name-tool.md) и команды компилятора для вашего языка.

### <a name="to-install-the-validator-into-the-target-computer"></a>Установка проверяющего элемента управления на целевом компьютере

1. Установите проверяющий элемент конечной точки, используя соответствующую процедуру. На предприятии для этого можно использовать групповую политику или сервер Systems Management Server (SMS).

2. Установите сборку со строгим именем в глобальный кэш сборок с помощью [Gacutil.exe (средство глобального кэша сборок)](../../tools/gacutil-exe-gac-tool.md).

3. С помощью типов из пространства имен <xref:System.Configuration?displayProperty=nameWithType> выполните следующие действия.

    1. Добавьте расширение в раздел, [\<behaviorExtensions>](../../configure-apps/file-schema/wcf/behaviorextensions.md) используя полное имя типа, и заблокируйте элемент.

         [!code-csharp[LockdownValidation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#5)]

    2. Добавьте элемент Behavior в `EndpointBehaviors` свойство [\<commonBehaviors>](../../configure-apps/file-schema/wcf/commonbehaviors.md) раздела и заблокируйте элемент. (Чтобы установить проверяющий элемент управления в службе, проверяющий элемент управления должен быть <xref:System.ServiceModel.Description.IServiceBehavior> и добавлен к `ServiceBehaviors` свойству.) В следующем примере кода показана правильная конфигурация после шагов а. и B с единственным исключением, что в ней нет строгого имени.

        [!code-csharp[LockdownValidation#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#6)]

    3. Сохраните файл machine.config. В следующем примере кода выполняются все действия шага 3, но копия измененного файла machine.config сохраняется локально.

        [!code-csharp[LockdownValidation#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#7)]

## <a name="example"></a>Пример

В следующем примере кода показано, как добавить общее поведение в файл machine.config и сохранить копию файла на диске. `InternetClientValidatorBehavior`Берется из примера [проверки безопасности](../samples/security-validation.md) .

[!code-csharp[LockdownValidation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#1)]

## <a name="net-framework-security"></a>Безопасность .NET Framework

Может также возникнуть необходимость зашифровать элементы файла конфигурации. Дополнительные сведения см. в разделе «См. также».

## <a name="see-also"></a>См. также

- [Шифрование элементов файла конфигурации с помощью DPAPI](/previous-versions/msp-n-p/ff647398(v=pandp.10))
- [Шифрование элементов файла конфигурации с помощью RSA](/previous-versions/msp-n-p/ff650304(v=pandp.10))
