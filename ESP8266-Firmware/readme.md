
- 20190216 Ver. 0.4

Prima di caricare impostare il parametro Flash Size a : 4M (1M SPIFFS) altrimenti non viene  creato il File system.
La prima volta sarebbe meglio anche far cancellare completamente la memoria e non solo lo spazio sketch

Aggiunta la gestione mediante FS per i parametri:
//  - Indirizzo IP server MQTT
//  - Posta server MQTT
//  - Tipologia dispositivo/Identificativo non è il nome con qui si connette al server MQTT
//  Ho notato che se non vengono impostati correttamente i parametri per il WiFi e di conseguenza il nodo 
//  non si collega,i campi custom non vengono salvati

- 20190215

//Modificato host name del dispositivo, ora è identico al device MQTT
//20190211
//1) Ora il nodo all avvio manda le info su se stesso mediante una stringa json
//2) Aggiunto topic per chiedere info del nodo,come quelle inviate all'accensione
//3) Introdotto lampeggio ogni .2 sec durante l'attesa della connessione al server MQTT

*I COMANDI MQTT*

I comandi MQTT

ATS/(identificativo dispositivo)/MotorForward *[Speed]* (da 0 a 100)

ATS/(identificativo dispositivo)/MotorBackward *[Speed]* (da 0 a 100)

ATS/(identificativo dispositivo)/MotorStop

ATS/(identificativo dispositivo)/Reset

ATS/(identificativo dispositivo)/SoftReset

ATS/(identificativo dispositivo)/Info

- MotorForward/MotorBackward/MotorStop: controllano la porta 0 del controller (la porta 1 deve essere ancora implementata)
- Reset: reimpostano i setting del WiFi
- SoftReset: riavvia il dispositivo
- Info: restituisce via MQTT alcuni parametri del dispositivo:  DevId, Type, Speed, Dir, Ip
