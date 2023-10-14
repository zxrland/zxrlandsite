## racer.js
```javascript
const area1 = world.addZone({
    selector: 'player',
    bounds: {
        lo: [1, 8, 110],
        hi: [10, 10, 125],
    },
})
area1.onLeave(({ entity }) => {
    world.say(`${entity.player.name}出发了`)
    entity.starttime = new Date().getTime()
})
const area2 = world.addZone({
    selector: 'player',
    bounds: {
        lo: [109, 8, 2],
        hi: [116, 15, 3],
    },
})
area2.onEnter(({ entity }) => {
    if (entity.player.dead) return
    var usetimes = new Date().getTime() - entity.starttime
    world.say(`${entity.player.name}到达终点，用时${usetimes / 1000}秒`)
    if (usetimes / 1000 < entity.minTime) {
        entity.minTime = usetimes / 1000
        world.say(`恭喜${entity.player.name}破了自己记录`)
    }
    entity.mesh = entity.originPlayerMesh
    entity.enableDamage = false
    entity.player.invisible = false;
    entity.player.jumpPower = true
    entity.player.canFly = true;
    entity.player.runSpeed = 0.4 //默认值
    entity.player.walkSpeed = 0.22 //默认值
    entity.player.runAcceleration = 0.35   //控制玩家加速度
    entity.player.spawnPoint = new GameVector3(22, 94, 119)
    entity.player.forceRespawn()
})

world.onPlayerJoin(({ entity }) => {
    entity.minTime = Infinity
})

world.onChat(({ entity, message }) => {
    if (message == '/leaderboard') {
        pd = [] //排行榜得分
        pm = [] //排行榜名字
        world.querySelectorAll('player').forEach((entity) => { //遍历所有玩家
            pm.push(entity.player.name) //获取玩家名字
            pd.push(entity.minTime) //获取玩家得分
        })
        l = pd.length; //人数
        m = 0; //
        t1 = 0; //
        t2 = 0; //
        for (i = 0; i < l - 1; i++) {
            m = i; //i=人数-1
            for (j = i + 1; j < l; j++) {
                if (pd[j] < pd[m]) {
                    m = j;
                }
            }
            t1 = pd[i] //t1=排行榜得分的第
            t2 = pm[i]
            pd[i] = pd[m]
            pm[i] = pm[m]
            pd[m] = t1;
            pm[m] = t2
        }
        p = []
        for (n = 0; n < pd.length; n++) {
            p.push("第" + (n + 1) + "名：" + pm[n] + "：时间：" + pd[n])
        }
        entity.player.dialog({
            type: GameDialogType.SELECT,
            title: "排行榜",
            content: "已显示在线人员时间排行榜",
            options: p,
        })
    }
})
```
```
