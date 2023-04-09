## 速查表
`
world.onChat(async ({ entity, message }) => {
    if (entity.isPlayer) {
        if (admin.includes(entity.player.name)) {
            if (message == '特殊权限') { entity.player.directMessage('亲爱的创作人员你好！特殊功能包含日出、天亮、消失、傍晚、天黑、变大、变小、还原大小、封神、飞行、解除飞行、加速、隐身、现身、隐藏名字、显示名字、幽灵、解除幽灵、发光、还原发光、反光、还原反光、恢复血量、变红色、变蓝色、变绿色、变紫色、变黄色、变浅蓝色、还原颜色、瞬移、关闭瞬移、加血、清屏、        entity.position.set(Math.random() * 253, 15, Math.random() * 253);、全部还原、关闭粒子特效、开启粒子特效、禁言(例如:禁言+禁言者名字)、解除禁言(例如:解除禁言+被禁言者名字)、制裁(例如:制裁+被制裁者名字)、解除制裁(例如:解除制裁+被解除制裁者名字)') }
            if (message == '变大') { entity.player.scale += 3; world.say(entity.player.name + '变大了') }
            if (message == '变小') { entity.player.scale += -3; world.say(entity.player.name + '变小了') }
            if (message == '还原大小') { entity.player.scale = 1; world.say(entity.player.name + '还原了大小') }
            if (message == '飞行') { entity.player.canFly = true; world.say(entity.player.name + '开启了飞行模式') }
            if (message == '解除飞行') { entity.player.canFly = false; world.say(entity.player.name + '关闭了飞行模式') }
            if (message == '加速') {
                entity.player.walkSpeed += 1000
                entity.player.runSpeed += 1000
                entity.player.flySpeed += 1000
                world.say(entity.player.name + '加速了')
            }
            if (message === "日出") { world.sunPhase = 0; entity.player.directMessage('已设置到日出') }
            if (message == '变大') { entity.player.scale += 3; world.say(entity.player.name + '变大了') }
            if (message == '变小') { entity.player.scale += -0.5; world.say(entity.player.name + '变小了') }
            if (message == '还原大小') { entity.player.scale = 1; world.say(entity.player.name + '还原了大小') }
            if (message === "天亮") { world.sunPhase = 0.25; entity.player.directMessage('已设置到天亮') }
            if (message === "傍晚") { world.sunPhase = 0.5; entity.player.directMessage('已设置到傍晚') }
            if (message === "天黑") { world.sunPhase = 0.75; entity.player.directMessage('已设置到天黑') }
            if (message === "隐形") { entity.player.invisible = true; entity.player.directMessage('你已经打开隐形模式') }
            if (message === "解除隐形") { entity.player.invisible = false; entity.player.directMessage('你已经关闭隐形模式') }
            if (message == '回复血量') { entity.hp = 100; entity.maxHp = 100; world.say(entity.player.name + '回复了全部血量') }
            if (message == '无敌') { entity.hp = 5e10; entity.maxHp = 5e10; world.say(entity.player.name + '无敌了') }
            if (message == '隐身') { entity.player.invisible = true; world.say(entity.player.name + '隐身了') }
            if (message == '现身') { entity.player.invisible = false; world.say(entity.player.name + '现身了') }
            if (message == '隐藏名字') { entity.player.showName = false; world.say(entity.player.name + '隐藏了名字') }
            if (message == '显示名字') { entity.player.showName = true; world.say(entity.player.name + '显示了名字') }
            if (message == '幽灵') { entity.player.spectator = true; world.say(entity.player.name + '开启了幽灵模式') }
            if (message == '解除幽灵') { entity.player.spectator = false; world.say(entity.player.name + '关闭了幽灵模式') }
            if (message == '发光') { entity.player.emissive = 1; world.say(entity.player.name + '开启了发光效果') }
            if (message == '还原发光') { entity.player.emissive = 0; world.say(entity.player.name + '还原了发光效果') }
            if (message == '反光') { entity.player.shininess = 1; world.say(entity.player.name + '开启了反光效果') }
            if (message == '还原反光') { entity.player.shininess = 0; world.say(entity.player.name + '还原了反光效果') }
            if (message == '变红色') { entity.player.color.set(1, 0, 0); world.say(entity.player.name + '变成了红色') }
            if (message == '变蓝色') { entity.player.color.set(0, 0, 1); world.say(entity.player.name + '变成了蓝色') }
            if (message == '变绿色') { entity.player.color.set(0, 1, 0); world.say(entity.player.name + '变成了绿色') }
            if (message == '变紫色') { entity.player.color.set(1, 0, 1); world.say(entity.player.name + '变成了紫色') }
            if (message == '变黄色') { entity.player.color.set(1, 1, 0); world.say(entity.player.name + '变成了黄色') }
            if (message == '变浅蓝色') { entity.player.color.set(0, 1, 1); world.say(entity.player.name + '变成了浅蓝色') }
            if (message == '还原颜色') { entity.player.color.set(1, 1, 1); world.say(entity.player.name + '还原了颜色') }
`
