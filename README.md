Прошивка анализирует состояние входа A7 MMC ACC (появляется при включении зажигания), анализ включеного MMC берётся с питания USB-входа MMC.
Управление MMC осуществляется подачей низкого уровня на круглую кнопку MMC.

Логика работы:

1. При включении зажигания, на A7 появляется напряжение +12В. Через делитель напряжения (на резисторах) 5В подаётся на ардуино. Ардуино понимает, что включено зажигание и подаёт в течении 1-2 сек. напряжение низкого уровня на контакты центральной круглой кнопки MMC. MMC включается.
2. Если напряжение на A7 прпадает, а MMC включено (определяется по напряжению на выходе USB MMC), то включается таймер и через 3 минуты подаётся низкое напряжение на кнопку и MMC выключается.
3. Если MMC выключено а пользователь сам нажал на кнопку включения MMC, то MMC включается, а ардуино включает таймер на 40 минут, после истечения которого - ардуино выключит MMC.
4. Если MMC включено через зажигание, но пользователь сам выключил её через кнопку, то ардуино не будет включать MMC при появлении питания на A7. Чтобы вернуться в обычный режим - нужно включить MMC кнопкой.
