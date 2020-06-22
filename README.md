# Comandos Basicos de Moderacion 👮
Simples comandos de moderacion echos en command handler

• En español

• Command Handler

• Discord.js v11.5.1

# Comando Ban (Handler)

const Discord = require('discord.js')

module.exports.run = async (bot, message, args) => {


  ```js
  let user = message.mentions.users.first();
  let razon = args.slice(1).join(" ");
  var perms = message.member.hasPermission("BAN_MEMBERS");
  if(!perms) return message.channel.send("**❌ No tienes permisos para ejecutar este comando.**")
  if(!user) return message.channel.send("❌ **Debes mencionar al usuario que quieres banear**")
  if(!razon) return message.channel.send("**❌ Debes escribir la razon por la cual lo baneas**")
  if (!message.guild.member(user).bannable) return message.reply("**❌ No puedo banear a ese usuario.**")
  message.guild.member(user).ban(razon);
  const embed = new Discord.RichEmbed()
  .setThumbnail(user.avatarURL)
  .addField("Usuario:", `${user}`)
  .addField("ID del usuario:", `${user.id}`)
  .addField("Razon:", `${razon}`)
  .addField("Autor del baneo:", `${message.author}`)
  message.channel.send(embed)
}```

#HOLA



