const { Client, LocalAuth } = require('whatsapp-web.js');
const qrcode = require('qrcode-terminal');

const client = new Client({
    authStrategy: new LocalAuth(),
    puppeteer: { args: ['--no-sandbox', '--disable-setuid-sandbox'] }
});

client.on('qr', qr => {
    qrcode.generate(qr, {small: true});
    console.log(qr);
});

client.on('ready', () => {
    console.log('BOT ONLINE');
});

client.on('message', async msg => {
    if(msg.body === '/würfel'){
        msg.reply(`🎲 ${Math.floor(Math.random()*6)+1}`);
    }
});

client.initialize();
