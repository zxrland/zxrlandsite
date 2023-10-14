## second-manager.js
```javascript
let hmd = []  
let ban = (name) => hmd.push(name);
let je = (name) => hmd.splice(hmd.indexOf(name), 1);



world.onPlayerJoin(({ entity }) => {
    if (hmd.includes(entity.player.name)) {
        world.say(`@${entity.player.name}已踢出`)
        entity.player.kick()
    }
})
const canfly = []
const xiedian = ['zxr6247', '好奇的土岩龙HHaS','ZiLingKiller','Ay.Cyan.Bamboo.','克尼里斯','SEN.陈某文','迷失幻境']
//const xiedian = ['zxr6247','ZiLingKiller']
world.onPlayerJoin(({ entity }) => {
    if (!canfly.includes(entity.player.name)) return;
    else entity.player.canFly = true; entity.player.flySpeed *= 2; entity.player.flyAcceleration *= 2
})
world.onChat(async ({ entity, message }) => {
    if (message[0] == "$") {
        if (xiedian.includes(entity.player.name)) {
            try {
                var code = eval(message.slice(1));
                world.say(`~>${code}`)
            }
            catch (e) {
                world.say(e)
            }
        }
    }
    /*if (message.indexOf('$') == 0) {
        if (canfly.includes(e.player.name)) {
            try {
                wa()
                world.say('~>' + eval(message.slice(1)));
            } catch (error) {
                world.say('Error:' + error);
            }
        }
        if (xiedian.includes(e.player.name)) {
            try {
                world.say("执行代码[管理员]")
                world.say('~>' + eval(message.slice(1)));
            } catch (error) {
                world.say('Error:' + error);
            }
        }
    }*/
})
```
