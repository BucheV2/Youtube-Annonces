const Discord = require('discord.js');

var bot = new Discord.Client();
var prefix = (".");
var randnum = 0;

function random(min, max) {
    min = Math.ceil(1);
    max = Math.floor(10);
    randnum = Math.floor(Math.random() * (max - min +1) + min);
}

bot.on('ready ',()=>{
    bot.user.setPresence({ game: { name: '.help | Buche__ 💙' , type: 0}});
    console.log("Bot Ready !");
});


bot.login('NDYxOTU2MDA1NTg0OTYxNTc2.Dj8jHA.z9hSIPYOyzJT-PCF8rVxv_GBLog');

bot.on('message', message => {
    if (message.content === prefix + "ping"){
        message.channel.sendMessage("Pong! :ping_pong:");
        console.log('ping pong');

    }

    if (message.content === prefix + "help"){
        message.channel.sendMessage("**Commandes disponnibles :**");
        var help_embed = new Discord.RichEmbed()
            .setColor('#01BDFF')
            .addField("Commandes de MODERATION! :hammer:", "Voici les commandes:")
            .addField("!ban [Membre] (Raison)", "Banni un joueur du serveur")
            .addField("!unban [Membre]", "Débanni un joueur du serveur")
            .addField("!mute [Membre] [Temps] (Raison)", "Fait taire la personne")
            .addField("!unmute [Membre]", "Re-ouvre la bouche de la personne")
            .addField("!warn [Membre] (Raison)", "Avertit la personne")
            .addField("!unwarn [Membre] (Nom du warn)", "Retire l'avertissement")
            .addField("!clear [Mombre de messages]", "Supprime des messages")
        var help_embed1 = new Discord.RichEmbed()
            .setColor('#01BDFF')
            .addField("Les commandes FUN! :tada:", "``Fais-toi plaisir! 😁``")
            .addField("!flip", "Pile ou Face? Pile!")
            .addField("!shifumi", "1.. 2.. 3... Pierre, feuille, ciseaux? ``😂``")
            .addField("!nombre", "Devinez le nombre que j'ai en tête! 21? 65? Non.. Essaies encore.")
            .addField("!kill", "BOOOOM! T'es mort ``😕``")
        message.channel.sendEmbed(help_embed);
        message.channel.sendEmbed(help_embed1);
        //message.channel.sendMessage("Voici les commandes disponnible!");
        console.log("help fais");
    } 

    if (message.content === prefix + "kill"){
        random();

        if (randnum == 1){
            message.channel.sendMessage("Tu viens de mourrir de suffocation 💦");
            console.log("KILL-REPONSE-1");
        }
        
        if (randnum == 2){
            message.channel.sendMessage("Tu meurt soudain d'une chute d'escalier ... 💐");
            console.log("KILL-REPONSE-2");
        }

        if (randnum == 3){
            message.channel.sendMessage("Sérieusement? Tu as réussis à te faire une entorce à la cheville? Attention un Camion! 🚛\nIl fallait passer sur le passage pieton ...");
            console.log("KILL-REPONSE-3");
        }

        if (randnum == 4){
            message.channel.sendMessage("S'est prit les bâtons dans les roues 💩 ");
            console.log("KILL-REPONSE-4");
        }

});
