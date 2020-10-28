
# whatsapp-tme
Um cliente de API do WhatsApp que se conecta por meio do aplicativo de navegador da Web WhatsApp

Ele usa o Puppeteer para executar uma instância real do Whatsapp Web para evitar o bloqueio.

NOTA: Não posso garantir que você não será bloqueado com esse método, embora tenha funcionado para mim. O WhatsApp não permite bots ou clientes não oficiais em sua plataforma, então isso não deve ser considerado totalmente seguro.

## Installation

The module is now available on npm! `npm i whatsapp-tme`

Please note that Node v10.18.1+ is required due to Puppeteer.

## Example usage

```js
const { Client } = require('whatsapp-tme');
const client = new Client();

client.on('qr', (qr) => {
    // Generate and scan this code with your phone
    console.log('QR RECEIVED', qr);
});

client.on('ready', () => {
    console.log('Client is ready!');
});

client.on('message', msg => {
    if (msg.body == '!ping') {
        msg.reply('pong');
    }
});

client.initialize();
```

Dê uma olhada em [example.js] (https://github.com/TalalMohamedElmenoufi/whatsapp-tme/blob/master/example.js) para outro exemplo com mais casos de uso.

## Recursos com suporte

| Feature  | Status |
| ------------- | ------------- |
| Send messages  | ✅  |
| Receive messages  | ✅  |
| Send media (images/audio/documents)  | ✅  |
| Send media (video)  | ✅ [(requires google chrome)](https://github.com/TalalMohamedElmenoufi/whatsapp-tme/issues/78#issuecomment-592723583)  |
| Send stickers | _pending_ |
| Receive media (images/audio/video/documents)  | ✅  |
| Send contact cards | ✅ |
| Send location | ✅ |
| Receive location | ✅ | 
| Message replies | ✅ |
| Join groups by invite  | ✅ |
| Get invite for group  | ✅ |
| Modify group info (subject, description)  | ✅  |
| Modify group settings (send messages, edit info)  | ✅  |
| Add group participants  | ✅  |
| Kick group participants  | ✅  |
| Promote/demote group participants | ✅ |
| Mention users | ✅ |
| Mute/unmute chats | ✅ |
| Get contact info | ✅ |
| Get profile pictures | ✅ |
| Set user status message | ✅ |

Something missing? Make an issue and let us know!

## Links

* [Reference](https://github.com/TalalMohamedElmenoufi/whatsapp-tme)
* [GitHub](https://github.com/TalalMohamedElmenoufi/whatsapp-tme)

## Contribuindo

Solicitações pull são bem-vindas! Se você vir algo que gostaria de adicionar, faça-o. Para mudanças drásticas, abra um problema primeiro.

## Doando

Você pode apoiar o mantenedor deste projeto através do link abaixo

[![Support via https://elmenoufi.com.br)

## aviso Legal

Este projeto não é afiliado, associado, autorizado, endossado ou de qualquer forma oficialmente conectado ao WhatsApp ou a qualquer de suas subsidiárias ou afiliadas. O site oficial do WhatsApp pode ser encontrado em https://whatsapp.com. "WhatsApp", bem como nomes, marcas, emblemas e imagens relacionados são marcas registradas de seus respectivos proprietários.

## License

Copyright 2020 Talal Mohamed

Licenciado sob a Licença Apache, Versão 2.0 (a "Licença");
você não pode usar este projeto, exceto em conformidade com a Licença.
Você pode obter uma cópia da Licença em http://www.apache.org/licenses/LICENSE-2.0.

A menos que exigido pela lei aplicável ou acordado por escrito, software
distribuído sob a Licença é distribuído "COMO ESTÁ",
SEM GARANTIAS OU CONDIÇÕES DE QUALQUER TIPO, expressas ou implícitas.
Consulte a Licença para as permissões específicas que regem o idioma e
limitações sob a Licença.
