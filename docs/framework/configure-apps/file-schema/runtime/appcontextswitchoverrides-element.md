---
title: Элемент AppContextSwitchOverrides
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
ms.openlocfilehash: 8d5cd73bb9393533cb669581420e24297cb5ff71
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102935"
---
# <a name="appcontextswitchoverrides-element"></a>\<Элемент AppContextSwitchOverrides>

Определяет один или несколько коммутаторов, используемых классом <xref:System.AppContext> для предоставления механизма отказа от новых функциональных возможностей.

[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<>AppContextSwitchOverrides**

## <a name="syntax"></a>Синтаксис

```xml
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`value`|Обязательный атрибут.<br /><br /> Определяет одно или несколько имен переключателей и связанных с ними значений Boolean.|

### <a name="value-attribute"></a>значение атрибута

|Значение|Описание|
|-----------|-----------------|
|"имя-значение"|Предопределенное имя переключателя вместе`true` `false`с его значением (или). Несколько пар имени/значения переключателя разделены запятыми (";»). Список предопределенных имен коммутаторов, поддерживаемых рамочной рамкой .NET, см.|

### <a name="child-elements"></a>Дочерние элементы
 Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|

## <a name="remarks"></a>Remarks
 Начиная с .NET Framework 4.6, `<AppContextSwitchOverrides>` элемент в файле конфигурации позволяет абонентам API определить, может ли их приложение воспользоваться новой функциональностью или сохранить совместимость с предыдущими версиями библиотеки. Например, если поведение API изменилось между двумя версиями `<AppContextSwitchOverrides>` библиотеки, элемент позволяет абонентам этого API отказаться от нового поведения в версиях библиотеки, поддерживающих новую функциональность. Для приложений, которые вызывают AI `<AppContextSwitchOverrides>` в рамках .NET, элемент может также позволить абонентам, чьи приложения нацелены на более раннюю версию рамочной программы .NET, выбрать новую функциональность, если их приложение работает на версии рамочной системы .NET, которая включает эту функциональность.

 Атрибут `value` `<AppContextSwitchOverrides>` элемента состоит из одной строки, которая состоит из одной или нескольких пар с разграничением между запятыми колонами и значениями.  Каждое имя определяет переключатель совместимости, и его соответствующим`true` `false`значением является Boolean (или), что указывает на то, установлен ли переключатель. По умолчанию коммутатор является, `false`и библиотеки предоставляют новую функциональность. Они обеспечивают только предыдущую функциональность, если коммутатор `true`установлен (т.е. его значение). Это позволяет библиотекам предоставлять новое поведение для существующего API, позволяя абонентам, которые зависят от предыдущего поведения, отказаться от новой функциональности.

Рамочный проект .NET поддерживает следующие коммутаторы:

|Имя переключателя|Описание|Введенный|
|-----------------|-----------------|----------------|
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Контролирует, использует ли Windows Presentation Foundation устаревший алгоритм управления. Дополнительные сведения см. в разделе [Устранение рисков. Макет WPF](../../../migration-guide/mitigation-wpf-layout.md).|.NET Framework 4.6|
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|Контролирует ли алгоритм по умолчанию, используемый для подписания частей пакета PackageDigitalSignatureManager SHA1 или SHA256.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|При установке на `false`, позволяет отладки XAML на основе рабочих процессов проектов с Visual Studio, когда FIPS включен. Без него, <xref:System.NullReferenceException> в вызовы к методам в Сборке System.Activities брошены призывы к методам.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|Контролирует, использует ли проверка экземпляра рабочего процесса в отладчике MD5 или SHA1. | .NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseSHA1HashForDebuggerSymbols`|Контролирует ли хэширование checksum рабочего процесса использует алгоритм SHA1, введенный`true`по умолчанию в .NET Framework 4.7 ( или же он`false`использует алгоритм SHA256 по умолчанию, введенный по умолчанию в .NET Framework 4.8 ( ).<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.8|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|Контролирует, получают ли следы стека при использовании портативных PDB, может включать исходный файл и информацию о строке. `false`включить исходный файл и информацию о строках; в `true`противном случае, .|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Контролирует, <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> бросает ли метод исключение, когда <xref:System.Drawing.Icon> объект имеет кадры PNG. Дополнительные сведения см. в разделе [Устранение рисков: кадры PNG кадров в объектах Icon](../../../migration-guide/mitigation-png-frames-in-icon-objects.md).|.NET Framework 4.6|
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|Определяет, <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> правильно ли удаляются объекты <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType> при добавлении в коллекцию методом. `true`для поддержания устаревшего поведения; `false` распоряжаться всеми частными объектами шрифта. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`<br>`OptimizePrintPreview`|Контролирует, оптимизирована <xref:System.Windows.Forms.PrintPreviewDialog> ли производительность для сетевых принтеров. Для получения дополнительной информации [см.](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md)|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceJapaneseEraYearRanges`|Контролирует, применяются ли проверки диапазонов в течение года для японских календарных эр. `true`для обеспечения проверки `false` диапазона год, и отключить их (поведение по умолчанию). Для получения дополнительной [информации см.](../../../../standard/datetime/working-with-calendars.md)|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceLegacyJapaneseDateParsing`|Контролирует, признается ли только "1" первым годом японской календарной эры при разборе операций. `true`распознать только "1"; `false` распознать "1" или Gannen (поведение по умолчанию). Для получения дополнительной [информации см.](../../../../standard/datetime/working-with-calendars.md)|.NET Framework 4.6|
|`Switch.System.Globalization.FormatJapaneseFirstYearAsANumber`|Контролирует, представлен ли первый год японской календарной эры как "1" или Gannen в операциях форматирования. `true`для формата первого года эпохи как "1"; `false` для форматирования его как Gannen (поведение по умолчанию). Для получения дополнительной [информации см.](../../../../standard/datetime/working-with-calendars.md)|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Контролирует, не вытекают ли асинхронные операции из контекста вызывающей потока. Для получения дополнительной информации [см.](../../../migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks)|.NET Framework 4.6|
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Контролирует, <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> пытается ли метод сопоставить тип претензии только с последней записью DNS. Дополнительные сведения см. в разделе [Устранение рисков: метод X509CertificateClaimSet.FindClaims](../../../migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|.NET Framework 4.6.1|
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|Контролирует, следует ли разрешить AuthorizationContext.Empty возвращать изменяемый объект.|.NET Framework 4.6|
|`Switch.System.IO.BlockLongPaths`|Контролирует ли пути `MAX_PATH` дольше, чем (260 символов) бросить <xref:System.IO.PathTooLongException>. Для получения дополнительной [Long Path Support](../../../migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support)информации см.|.NET Framework 4.6.2|
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|Контролирует, используются ли нативные процедуры <xref:System.IO.Compression.DeflateStream> ОС для декомпрессии классом. `false`использовать родные AIS; `true` использовать <xref:System.IO.Compression.DeflateStream> реализацию.|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Использует backslash (""),\\а не передний слэш ("/") <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> в качестве сепаратора пути в свойстве. Для получения более подробной информации, [см. Смягчение: SipArchiveEntry.FullName Путь сепаратор](../../../migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|.NET Framework 4.6.1|
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|Контролирует, прекращают ли процесс исключения операционной <xref:System.IO.Ports.SerialPort> системы, которые выбрасываются на фоновые потоки, созданные потоками.|.NET Framework 4.7.1|
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Контролирует, используется ли нормализация устаревшего пути, <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> а пути URI поддерживаются методами. <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> Для получения дополнительной информации [см. Смягчение: Путь нормализации](../../../migration-guide/mitigation-path-normalization.md) и [смягчения последствий: Путь Colon проверки](../../../migration-guide/mitigation-path-colon-checks.md).|.NET Framework 4.6.2|
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Контролирует, сравнивает ли тест <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> на равенство свойство одного объекта с <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> свойством второго объекта. Для получения дополнительной [информации см. Неправильная реализация MemberDescriptor.Equals](../../../migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals).|.NET Framework 4.6.2|
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Сертификат «Отключители» улучшил проверку идентификатора объектов использования ключей (EKU). Расширение расширенного использования ключа (EKU) — это коллекция идентификаторов объекта (OID), которые указывают приложения, использующие ключ.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Отключает TLS1.0 Browser Exploit против SSL/TLS (BEAST) путем отключения использования SCH_SEND_AUX_RECORD.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Контролирует, <xref:System.Net.ServicePointManager?displayProperty=nameWithType> может <xref:System.Net.Security.SslStream?displayProperty=nameWithType> ли класс и классы использовать протокол SSL 3.0. Дополнительные сведения см. в разделе [Устранение рисков. Протоколы TLS](../../../migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Отражает версии SystemDefault TLS, возвращающиеся к дефолту Tls12, Tls11, Tls.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Отражает оповещения на стороне сервера SslStream TLS.|.NET Framework 4.7|
|`Switch.System.Runtime.InteropServices.`<br/>`DoNotMarshalOutByrefSafeArrayOnInvoke`|Контролирует ли ByRef SafeArray параметры на COM interop`false`событий маршал обратно в родной код`true`() или же маршал обратно в родной код отключен ( ).|.NET Framework 4.8|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Контролирует, является ли [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) сериализирующим некоторые контрольные символы на основе стандартов ECMAScript V6 и V8. Дополнительные сведения см. в статье [Устранение рисков. Сериализация управляющих символов с помощью DataContractJsonSerializer](../../../migration-guide/mitigation-serialization-control-characters.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|Контролирует ли <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> поддерживает несколько корректировок или только одну корректировку для часового пояса. Если, `true`он <xref:System.TimeZoneInfo> использует тип для сериализации и десеризывизации данных о дате и времени; в противном <xref:System.TimeZone> случае он использует тип, который не поддерживает несколько правил корректировки.|.NET Framework 4.6.2|
|`Switch.System.Runtime.Serialization.UseNewMaxArraySize`|Контролирует, <xref:System.Runtime.Serialization.ObjectManager?displayProperty=nameWithType> использует ли больший размер массива во время сериализации и десериализации объектов. Установите этот `true` переключатель для улучшения производительности сериализации и десеризацию <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>больших графиков объектов по типам, таким как . |.NET Framework 4.7.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Контролирует, <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29> устанавливает ли конструктор свойство <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> нового объекта с помощью существующей ссылки объекта. Дополнительные сведения см. в разделе [Устранение рисков. Конструктор ClaimsIdentity](../../../migration-guide/retargeting/4.6.1-4.6.2.md).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Контролирует, является ли попытка <xref:System.Security.Cryptography.AesCryptoServiceProvider> повторного использования <xref:System.Security.Cryptography.CryptographicException>расшифровщика бросает . Для получения дополнительной [AesCryptoServiceProvider decryptor provides a reusable transform](../../../migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform)информации см.|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Контролирует, является ли значение свойства [CspParameters.ParentWindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) [intPtr,](xref:System.IntPtr) представляющего расположение памяти ручки окна, или же это ручка окна (HWND). Дополнительные сведения см. в статье [Mitigation: CspParameters.ParentWindowHandle Expects an HWND](../../../migration-guide/retargeting/4.6.2-4.7.md#cspparametersparentwindowhandle-now-expects-hwnd-value) (Устранение рисков. CspParameters.ParentWindowHandle ожидает HWND). |.NET Framework 4.7|
|`Switch.System.Security.Cryptography.`<br/>`UseLegacyFipsThrow`|Контролирует ли использование управляемых классов криптографии в <xref:System.Security.Cryptography.CryptographicException> `true`режиме FIPS бросает a (`false`) или полагается на реализацию системных библиотек ().|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|Определяет, является ли значение по умолчанию для некоторых операций SignedCMS SHA1 или SHA256.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.X509Certificates.`<br/>`ECDsaCertificateExtensions.UseLegacyPublicKeyReader`|Контролирует, <xref:System.Security.Cryptography.X509Certificates.ECDsaCertificateExtensions.GetECDsaPublicKey%2A?displayProperty=nameWithType> правильно ли метод обрабатывает все названные кривые, поддерживаемые операционной системой ()`false`или возвращается к устаревшему поведению.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|Определяет, является ли значение по умолчанию для некоторых операций SignedXML SHA1 или SHA256.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Определяет, позволяет `TransportWithMessageCredential` ли режим безопасности сообщения с неподписанным заголовком "к". Это переключатель выбора. Для получения дополнительной информации [см.](../../../migration-guide/runtime/4.5.2-4.6.1.md#windows-communication-foundation-wcf)|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|Контролирует ли <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> конструктор бросает, <xref:System.ArgumentException> если один из `null`элементов.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Определяет, является ли попытка использования сертификатов X509 с поставщиком ключей хранилища CSG выбрасывает исключение. Для получения дополнительной информации см. [WCF transport security поддерживает сертификаты, хранящиеся с помощью CNG.](../../../migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng)|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|При использовании переноса HTTP с самостоятельной службой, установка этого значения `true` `Connection: close` для того, чтобы WCF проигнорировала приложение, добавляющее заголовок ответа в заголовки ответов для запроса. Установка этого `false` значения позволяет `Connection: close` добавлять заголовок в заголовки ответов, что приводит к закрытию разъема запроса после отправки ответа.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|Ручки взаимоблокировок, которые возникают в результате ограничения экземпляров службы повторного доступа к одному потоку выполнения за один раз.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Наряду `Switch.System.Net.DontEnableSchUseStrongCrypto`с , определяет, использует ли wCF безопасность сообщений TLS 1.1 и TLS 1.2.|.NET Framework 4.7 |
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|Значение `false` устанавливает конфигурацию по умолчанию, чтобы позволить операционной системе выбрать протокол. Значение `true` устанавливает значение по умолчанию к самому высокому доступному протоколу. (Также доступна на обслуживании ветви предыдущих рамочных версий)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|Определяет, является ли алгоритм подписания сообщения по умолчанию для сообщений MsM в WCF SHA1 или SHA256.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|Контролирует, использует ли WCF sha1 или хэш SHA256 для генерации случайных имен для названных труб.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|Контролирует, следует ли бросать [NullReferenceException,](xref:System.NullReferenceException) когда сообщение исключения является нулевым.|.NET Framework 4.7|
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|Контролирует, распространяются ли исключения, брошенные на запуск сервиса, <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> на вызывающей метод.|.NET Framework 4.7.1|
|`Switch.System.Threading.UseNetCoreTimer`|Контролирует, <xref:System.Threading.Timer> используют ли экземпляры преимущества повышения производительности для крупномасштабных сред. Если `true`включено улучшение производительности; если `false` (значение по умолчанию) они отключены.|.NET Framework 4.8|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|Определяет, постоянно ли остаются закодированными некоторые символы, закодированные процентом, которые иногда были расшифрованы. Если `true`они расшифроваются; в `false`противном случае, .|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Определяет обработку двухнаправленных символов Unicode в URIs. `true`лишить их УРИ; `false` сохранить и закодировать их на процент.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Определяет, применяет ли Windows Presentation Foundation`true`старый алгоритм`false`() или новый алгоритм () при выделении места \*в столбцы. Дополнительные сведения см. в статье [Mitigation: Grid Control's Space Allocation to Star-columns](../../../migration-guide/retargeting/4.6.2-4.7.md#wpf-grid-allocation-of-space-to-star-columns) (Устранение рисков. Выделение пространства элемента управления "сетка" для столбцов со звездочкой). |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|Контролирует, всегда ли селектор или элемент управления вкладками обновляет значение выбранного свойства значения перед повышением измененного события выбора.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|Определяет, доступна ли рендеринг выбора на основе <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.PasswordBox> не-Adorner для элементов`false`управления для предотвращения окклюзионного`true`текста (), или же текст отображается только в слое Adorner ( ).|.NET Framework 4.7.2|
|`Switch.System.Windows.Data.Binding.`<br/>`IListIndexerHidesCustomIndexer`|Контролирует, используются ли пользовательские индексы IList неправильно ()`true`или правильно ()`false`по классу. <xref:System.Windows.Data.Binding?displayProperty=nameWithType>|.NET Framework 4.8|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|Определяет, происходят ли изменения DPI на системе `false`(значение) или на основе `true`монитора (значение).|.NET Framework 4.6.2|
|`Switch.System.Windows.`<br/>`DoNotUsePresentationDpiCapabilityTier2OrGreater`|Контролирует ли улучшения в размерах <xref:System.Windows.Interop.HwndHost?displayProperty=nameWithType> элементов управления в случае, когда WPF работает в режиме сознаваемого монитора , отключены ()`true`или включены (`false`).|.NET Framework 4.8|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|Определяет, нужно ли разработчику <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> специально обрабатывать действие при наличии текста управления. `true`для обработки <xref:System.Windows.Forms.DomainUpDown.UpButton> действия; `false` для <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> правильного синхронизации и <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> действий.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|Отказывается от кода, который <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> позволяет пользовательской реализации безопасно фильтровать <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> сообщения, не бросая исключения при вызове метода. Дополнительные сведения см. в разделе [Устранение рисков: пользовательские реализации IMessageFilter.PreFilterMessage](../../../migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|.NET Framework 4.6.1|
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|Определяет, возвращает <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> ли свойство исходный элемент управления, когда <xref:System.Windows.Forms.ToolStripMenuItem> пользователь открывает меню из вложенного элемента управления. `true`вернуться, `null`наследие поведения; `false` вернуть элемент управления исходным источником.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.UseLegacyToolTipDisplay`|Контролирует ли поддержка вызова tooltip`true`отключена`false`() или включена (). Включение поддержки вызова tooltip также требует `Switch.UseLegacyAccessibilityFeatures`устаревших `Switch.UseLegacyAccessibilityFeatures.3` функций доступности, `false`определенных , `Switch.UseLegacyAccessibilityFeatures.2`и все быть отключены (установить).|.NET Framework 4.8|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Определяет, включен `WM_POINTER`ли в приложениях WPF дополнительный стек касания/стилуса. Для получения дополнительной информации [см.](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|Определяет, является ли алгоритм хэша по умолчанию,`false`используемый для`true`проверки, SHA256 ( ) или SHA1 ().<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|Контролирует, брошен ли наследный [NullReferenceException](xref:System.NullReferenceException) вместо исключения, которое более конкретно указывает причину исключения (например, [DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException) или [FileNotFoundException.](xref:System.IO.FileNotFoundException) Предназначен для использования кодом, который зависит от обработки [NullReferenceException.](xref:System.NullReferenceException) | .NET Framework 4.7 |
|`Switch.System.Workflow.ComponentModel.`<br/>`UseLegacyHashForXomlFileChecksum`|Контролирует ли хэширование xOML файлов в сборках рабочего процесса`true`с помощью алгоритма MD5 (), или же они используют алгоритм SHA256, введенный по умолчанию в .NET Framework 4.8.<br>Из-за конфликта с MD5 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForSqlTrackingCacheKey`|Контролирует ли хэширование checksum sslTrackingService с`true`помощью алгоритма MD5 () для кэшированных строк, или же он использует алгоритм SHA256, введенный по умолчанию в .NET Framework 4.8.<br>Из-за конфликта с MD5 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForWorkflowDefinitionDispenserCacheKey`|Контролирует, использует ли хэширование checksum workflow Runtime`true`алгоритм MD5 () для определения кэшированных рабочих процессов, или же он использует алгоритм SHA256, введенный по умолчанию в .NET Framework 4.8.<br>Из-за конфликта с MD5 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.8|
|`Switch.UseLegacyAccessibilityFeatures`|Контролирует, включены или отключены функции доступности, начиная с .NET Framework 4.7.1. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|Контролирует ли доступ функции, доступные в .NET`false`Framework 4.7.2 включены ( ) или отключены (`true`). `true`Если, `Switch.UseLegacyAccessibilityFeatures` также `true` должны быть включить .NET Framework 4.7.1 функции доступности.|.NET Framework 4.7.2|
|`Switch.UseLegacyAccessibilityFeatures.3`|Контролирует ли функции доступности, введенные в`false`.NET Framework`true`4.8 включены ( ) или отключены ( ). `true`Если, `Switch.UseLegacyAccessibilityFeatures` `Switch.UseLegacyAccessibilityFeatures.2` и также `true`должны быть .|.NET Framework 4.8|
|`Switch.UseLegacyToolTipDisplay`|Контролирует, отображаются ли наборы инструментов, когда пользователь парит`true`курсор мыши над управлением WPF (), или`false`же они отображаются как на клавиатуре фокусировки и через клавишу клавиатуры ярлык ( , поведение по умолчанию). Для приложений, работающих на .NET Framework 4.8, но ориентированных на предыдущие версии .NET Framework, что позволяет как клавиатура фокусикат и ярлык ключевой поддержки требует, `Switch.UseLegacyAccessibilityFeatures`что `Switch.UseLegacyAccessibilityFeatures.2`, и `Switch.UseLegacyAccessibilityFeatures.3` все будет установлено `false`на .|.NET Framework 4.8|
|`Switch.System.Xml.`<br />`IgnoreEmptyKeySequences`|Контролирует, игнорируются ли пустые последовательности ключей в составных клавишах с помощью проверки схемы XSD. Для получения дополнительной информации [см.](../../../migration-guide/mitigation-xml-schema-validation.md)|.NET Framework 4.6|

> [!NOTE]
> Вместо `AppContextSwitchOverrides` добавления элемента в файл конфигурации приложения можно также запрограммовать коммутаторы, позвонив в `static` метод (в C) или `Shared` (в Visual Basic). <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>

 Разработчики библиотеки также могут определить пользовательские коммутаторы, чтобы абоненты могли отказаться от измененной функциональности, введенной в более поздних версиях библиотек. Дополнительные сведения см. в описании класса <xref:System.AppContext>.

## <a name="switches-in-aspnet-apps"></a>Переключатели в ASP.NET приложениях

Вы можете настроить ASP.NET приложение для использования настроек совместимости, добавив элемент [ \<Add>](../appsettings/add-element-for-appsettings.md) в [ \<раздел appSettings>](../appsettings/index.md) файла web.config.

В следующем примере `<add>` элемент добавляет сяруки в `<appSettings>` раздел файла web.config:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>Пример

 В следующем примере `AppContextSwitchOverrides` элемент определяет сяочание `Switch.System.Globalization.NoAsyncCurrentCulture`совместимости одного приложения, который предотвращает перетекания культуры по потокам в асинхронных вызовах метода.

```xml
<configuration>
   <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />
   </runtime>
</configuration>
```

 В следующем примере `AppContextSwitchOverrides` элемент определяется двумя переключателями `Switch.System.Globalization.NoAsyncCurrentCulture` `Switch.System.IO.BlockLongPaths`совместимости приложений и. Запятая разделяет две пары имен/значений.

```xml
<configuration>
    <runtime>
       <AppContextSwitchOverrides
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />
    </runtime>
</configuration>
```

## <a name="see-also"></a>См. также раздел

- [Смягчение нового поведения в рамках .NET 4.6 и позже](../../../migration-guide/mitigations.md)
- <xref:System.AppContext?displayProperty=nameWithType>
- [\<время выполнения> Элемент](runtime-element.md)
- [\<конфигурация> Элемент](../configuration-element.md)
