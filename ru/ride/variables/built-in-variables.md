# Встроенные переменные

**Встроенная переменная** — переменная [контекста скрипта](/ride/script/script-context.md).

| № | Имя | Описание |
| :--- | :--- | :--- |
| 1 | Buy | Тип [ордера](/blockchain/order.md) |
| 2 | height | [Высота блокчейна](/blockchain/blockchain/blockchain-height.md) в момент выполненияскрипта |
| 3 | lastBlock | Информация о последнем [блоке](/blockchain/block.md) блокчейна в момент выполнения скрипта |
| 4 | nil | Переменная, которая содержит пустой [список](/ride/data-types/list.md). Используется для создания списков. Например, вместо:<br>```let b = [5,6]```<br> можно написать:<br>```let a = 5::6::nil``` |
| 5 | 1. NOALG<br> 2. MD5<br> 3. SHA1<br> 4. SHA224<br> 5. SHA256<br> 6. SHA384<br> 7. SHA512<br> 8. SHA3224<br> 9. SHA3256<br> 10. SHA3384<br> 11. SHA3512<br> | Переменные, которые передаются в качестве первого параметра в  функцию[rsaVerify](/ride/functions/built-in-functions/verification-functions.md).<br> Все переменные, кроме NOALG, обозначают алгоритмы хеширования, которые применяются к данным. Если передать NOALG, то данные хешироваться не будут |
| 6 | Sell | Тип [ордера](/blockchain/order.md) |
| 7 | this | [Адрес](/blockchain/address.md) отправителя транзакции или информация о [токене](/blockchain/token.md) |
| 8 | tx | [Транзакция](/blockchain/transaction.md) или [ордер](/blockchain/order.md) |
| 9 | unit | Переменная, которая содержит объект типа [Unit](ru/ride/data-types/unit.md). Переменная используется программистом для получения объекта типа Unit. <br>**Пример 1**<br> Функция deposit переводит 5 [WAVELET](/blockchain/token/wavelet.md) на аккаунт, который [вызвал](/ride/functions/callable-function.md) эту функцию.<br> <xmp>{-# STDLIB_VERSION 3 #-}<br><br>{-# CONTENT_TYPE DAPP #-}<br>{-# SCRIPT_TYPE ACCOUNT #-} <br><br>@Callable(inv)<br>func deposit() = {<br>TransferSet([<br>ScriptTransfer(inv.caller, 5, unit) # Перевести 5 WAVELET на аккаунт inv.caller. Вместо ID токена указан unit<br>])<br>}</xmp><br> У WAVES нет [ID токена](/blockchain/token/token-id.md); вместо ID передается unit.<br>**Пример 2**<br>Функция [assetInfo](/ride/functions/built-in-functions/blockchain-functions.md) запрашивает информацию о токене по его ID. Далее функция isDefined проверяет, что токен с таким ID существует на блокчейне.<br><br><code>{-# STDLIB_VERSION 3 #-}<br>{-# CONTENT_TYPE EXPRESSION #-}<br>{-# SCRIPT_TYPE ACCOUNT #-}<br><br>let asset = assetInfo(base58'8LQW8f7P5d5PZM7GtZEBgaqRPGSzS3DfPuiXrURJ4AJS')<br>token.isDefined()</code> <br><br><br>Вместо вызова функции isDefined можно использовать равенство с unit.<br><br><code>asset != unit<br><br># Выражение asset != unit эквивалентно выражению token.isDefined()</code> |
