# Sensor_MPU_rev.1.0

Логика работы программы

Потоки:
1. Blink Led
2. Polling Sensor
3. UsartReceive
4. UsartTransmit

При старте программы поток Blink выполняет мигание раз в секунду, что означает ожидание запуска.

Поток UsartReceive смотрит, пришла ли команда на запуск. Когда пришла команда "StartSensor" с 
последовательного порта, в потоке UsartReceive проверяется эта команда на соответствие. Если
команда пришла правильная, то поток UsartReceive выставляет флаг о том, что можно опрашивать
сенсор.

Поток PollingSensor смотрит флаг от UsartReceive о старте работы. Флаг установлен, то происходит
инициализация сенсора и устана

