# Teste físico controlado — 0.16.0-s25-field1

Status: **controlled field-test candidate**. Não é release final.

## Preparação obrigatória

- Instalar/atualizar somente pela área **Atualizações** do próprio Live Segment.
- Confirmar versão `0.16.0-s25-field1`.
- Usar o aplicativo oficial iGPSPORT normalmente.
- **Não usar BLE Test** durante o pedal.
- Confirmar no preflight do Live: GPS preciso OK, Localização OK, BSC BLE OK, notificações do Live OK, canal BSC OK e acesso do iGPSPORT às notificações OK.

## Teste mínimo

1. Armar o Live antes do START.
2. Observar no BSC200 a notificação **START / COMEÇOU**.
3. Durante o trecho, confirmar pelo menos uma notificação normal de status.
4. Se for seguro e ocorrer naturalmente, provocar/observar uma desconexão e reconexão BLE longe dos gates e confirmar recuperação.
5. Se houver PAUSE real do BSC, confirmar que o tempo em movimento e o progresso não avançam durante a pausa.
6. No último quilômetro, observar as notificações de status final.
7. No gate final, confirmar **FINISH / FIM** uma única vez e que o Live encerra corretamente.
8. Preferencialmente repetir nos dois sentidos Recife → Paiva e Paiva → Recife.
9. Ao terminar, guardar o CSV do Live. Bugreport/BLE detalhado só é necessário se houver divergência real.

## Abort / rollback imediato

Interromper o teste e não promover a versão se ocorrer qualquer um destes pontos:

- crash ou ANR;
- relógio ou progresso regredir ou saltar de forma impossível;
- progresso avançar enquanto o BSC está PAUSED;
- START disparar indevidamente;
- FINISH não ocorrer, ficar preso ou duplicar;
- BLE desconectar e não recuperar;
- notificações START/status/km final/FINISH desaparecerem persistentemente no BSC200;
- comportamento do app divergir materialmente entre tela/log e BSC200.

## O que este teste prova

Ele valida a integração física real entre Live Segment, Android, iGPSPORT oficial e BSC200. Os testes automatizados já cobrem lógica de BLE, CCCD, reconnect, stale callbacks, START, FINISH, PAUSE, clock, lifecycle e replays reais IDA/VOLTA; o ponto ainda não demonstrado por software é a exibição efetiva das notificações no firmware/tela do BSC200 sob uso real.
