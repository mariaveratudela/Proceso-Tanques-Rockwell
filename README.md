# Proceso-Tanques-Rockwell-Studio5000
Código desarrollado para probar los actuadores del módulo de Rockwell de la UTEC con sus respectivos interlocks para evitar derrames de los tanques y daños en la bomba.

Conunbit(INICIO=1)
comenzar la ejecución de la siguiente secuencia:

- 1.Abrir DV10 y DV20
- 2.Una vez confirme DV10, abrir FV10 a un55%
- 3.Cuando FV10 llegue a su porcentaje, abrir DV30 
- 4.Una vez confirme DV20, abrir FV11 a un62%
- 5.Cuando FV11 llegue a su porcentaje, encender VF20 a velocidad 38.5 Hz
- 6.Habilitar interlocks de nivel alto para ambostanques (para evitar derrames) y nivel bajo para bomba.
- 7.Monitorear operación por emergencias

- Conunbit(INICIO=0) apagar el variador y cerrar todas las válvulas

INTERLOCKS DE SEGURIDAD:
- LAH(NivelT10>=300mm)--> Cerrar EV10
- LAHH(NivelT10>=350mm)--> Apagar Bomba
- LAHH(SwitchNivelAltoT20Activo)--> Cerrar EV20 y EV30
- LALL(SwitchNivelBajoT20Activo)--> ApagarBomba
