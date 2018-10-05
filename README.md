const Discord = require("discord.js");
const client = new Discord.Client();
const token = "prive";
var prefix = "g!";
var mention = "@NDk3MDMzMTAyNzM3MDE0Nzg0.Dpf6iQ.2Wf-Phpxlsb0zegj1NzgEr9lZAg";

client.on("ready", () => {
var servers = client.guilds.array().map(g => g.game).join(',');
console.log('I m ready');
});

var message = [];

client.on('message', message => {
if (message.content.startsWith(prefix + "help")) {
    message.channel.send('Bien les help sont facile parce que le bot et en text dans les prochaine mise à jour sa sera ameliorer');
}

else if (message.content.startsWith(prefix + "ping")) {
    var now = require('performance-now');
    var startTime = now();
    message.channel.send("pong = wait...").then(message => {
        var endTime = now();
        return message.edit("**pong ping_pong = " + Math.round(endTime - startTime));
    }).catch(console.error);
};

});
client.login(token);
