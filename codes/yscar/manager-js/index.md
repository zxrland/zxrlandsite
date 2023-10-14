## manager.js
```javascript
const manager = ['zxr6247', '好奇的土岩龙HHaS','迷失幻境','5星好市民', 'XGY.善良的宇宙兔yh', '机智的小黄鸡C7Pm', '冰封han', '甜甜的小梦x1', '错乱-纪元重生', 'ZiLingKiller', '小逸526', 'Ay.Cyan.Bamboo.','克尼里斯','SEN.陈某文']
//const manager = ['zxr6247',  '5星好市民', 'XGY.善良的宇宙兔yh', '冰封han', '甜甜的小梦x1', '错乱-纪元重生-科技与肃清', 'ZiLingKiller','小逸526']
world.onChat(async ({ entity, message }) => {
    if (!manager.includes(entity.player.name)) return
    if (message == '管理员特权') entity.player.directMessage('尊敬的管理员，你可以：变大、大小还原、发光、终极发光、飞行、解除飞行、还原颜色、变青、蓝、红、黄、绿、紫、黑、粉、橙、颜色还原、隐身、隐藏名字。显示名字、幽灵、取消幽灵、跳高、反光、金属感、第一人称视角、第三人称视角、下雨、停雨、下雪、停雪、起雾、停雾、取消玩家互相碰撞、允许玩家互相碰撞、瞬移至他人位置、他人瞬移至自己位置。')
    if (message == '俯视地图') {
        const lookTarget = new GameVector3(63, 8, 63);
        const lookEye = new GameVector3(63, 150, 63);
        const lookUp = new GameVector3(1, 0, 0)
        entity.player.dialog({
            type: GameDialogType.TEXT,
            content: `正在俯视中......`,
            lookEye: lookEye,
            lookTarget: lookTarget,
            lookUp: lookUp
        })
    }
    if (message == '全部还原') {
        entity.player.scale = 1;
        entity.zzss = 0
        entity.player.walkAcceleration = 0.22
        entity.player.runAcceleration = 0.35
        entity.player.skinInvisible.head = false
        entity.player.skinInvisible.hips = false
        entity.player.skinInvisible.leftFoot = false
        entity.player.skinInvisible.leftHand = false
        entity.player.skinInvisible.leftLowerArm = false
        entity.player.skinInvisible.leftLowerLeg = false
        entity.player.skinInvisible.rightFoot = false
        entity.player.skinInvisible.rightHand = false
        entity.player.skinInvisible.rightLowerArm = false
        entity.player.skinInvisible.rightLowerLeg = false
        entity.player.invisible = false;
        entity.player.showName = true;
        entity.player.spectator = false;
        entity.player.color.set(1, 1, 1);
        entity.player.canFly = false;
        entity.player.jumpPower = 0.96;
        entity.player.emissive = 0
        //entity.hp = 100;
        Object.assign(entity, {
            particleRate: 0
        })
    }
    if (message == '变大') { entity.player.scale = 6; world.say(entity.player.name + '变大了！') }
    if (message == '大小还原') { entity.player.scale = 1 }
    if (message == '发光') { entity.player.emissive = 0.5; world.say(entity.player.name + '的身上散发出了光芒！'); entity.player.directMessage('夜晚效果最佳(私)') }
    if (message == '终极发光') { entity.player.emissive = 999; world.say(entity.player.name + '的光芒照亮了地图！'); entity.player.directMessage('夜晚效果最佳（私）') }
    if (message == '飞行') { entity.player.canFly = true; world.say(entity.player.name + '开启了飞行模式') }
    if (message == '解除飞行') { entity.player.canFly = false }
    if (message == '还原颜色') { entity.player.color.set(1, 1, 1) }
    if (message == '变青') { entity.player.color.set(0, 1, 1); world.say(entity.player.name + '变青了') }
    if (message == '变蓝') { entity.player.color.set(0, 0, 1); world.say(entity.player.name + '变蓝了') }
    if (message == '变红') { entity.player.color.set(1, 0, 0); world.say(entity.player.name + '变红了') }
    if (message == '变黄') { entity.player.color.set(1, 1, 0); world.say(entity.player.name + '变黄了') }
    if (message == '变绿') { entity.player.color.set(0, 1, 0); world.say(entity.player.name + '变绿了') }
    if (message == '变紫') { entity.player.color.set(1, 0, 1); world.say(entity.player.name + '变紫了') }
    if (message == '变黑') { entity.player.color.set(0, 0, 0); world.say(entity.player.name + '变黑了') }
    if (message == '变粉') { entity.player.color.set(1, 0, 0.3); world.say(entity.player.name + '变粉了') }
    if (message == '变橙') { entity.player.color.set(1, 0.5, 0); world.say(entity.player.name + '变橙了') }
    if (message == '颜色还原') { entity.player.color.set(1, 1, 1) }
    if (message == '隐身') { entity.player.invisible = true; entity.player.showName = false; world.say(entity.player.name + '隐身了') }
    if (message == '隐藏名字') { entity.player.showName = false; world.say(entity.player.name + '隐藏了名字') }
    if (message == '显示名字') { entity.player.showName = true; world.say(entity.player.name + '显示了名字') }
    if (message == '幽灵') { entity.player.spectator = true; world.say(entity.player.name + '变成幽灵了') }
    if (message == '取消幽灵') { entity.player.spectator = false }
    if (message == '跳高') { entity.player.jumpPower += 3; world.say(entity.player.name + '跳得更高了') }
    if (message == '反光') { entity.player.shininess = 1; world.say(entity.player.name + '开启了反光模式') }
    if (message == '金属感') { entity.player.metalness = 1; world.say(entity.player.name + '开启了金属感效果') }
    if (message == '第一人称视角') { entity.player.cameraMode = GameCameraMode.FPS; world.say(entity.player.name + '切换到了第一人称视角') }
    if (message == '第三人称视角') { entity.player.cameraMode = GameCameraMode.FOLLOW; world.say(entity.player.name + '切换到了第三人称视角') }
    if (message == '下雨') { world.rainDensity = 0.5; world.say(entity.player.name + '使地图下起了雨') }
    if (message == '停雨') { world.rainDensity = 0; world.say(entity.player.name + '使地图停止了下雨') }
    if (message == '下雪') { world.snowTexture = 'snow/snow.part'; world.snowDensity = 0.1; world.say(entity.player.name + '使地图下起了雪') }
    if (message == '停雪') { world.snowDensity = 0; world.say(entity.player.name + '使地图停止了下雪') }
    if (message == '起雾') { world.fogUniformDensity = 0.1; world.say(entity.player.name + '使地图起了雾') }
    if (message == '停雾') { world.fogUniformDensity = 0; world.say(entity.player.name + '使地图停止了起雾') }
    if (message == '取消玩家之间碰撞') { world.addCollisionFilter('player', 'player') }
    if (message == '允许玩家之间碰撞') { world.removeCollisionFilter('player', 'player') }
    if (message == '大厅变飞机') { yd() }
    if (message == '重启') { world.say(`${entity.player.name}重启了地图`); while (1) { } }
    if (message == '瞬移至他人位置') {
        let options = []
        world.querySelectorAll('player').forEach((x) => {
            options.push(x.player.name)
        })
        const e = await entity.player.dialog({
            type: 'select',
            title: '他人位置',
            content: '你想瞬移至谁的位置？',
            options: options
        })
        if (e) {
            world.querySelectorAll('player').forEach((x) => {
                if (x.player.name == e.value) {
                    entity.position.set(x.position.x, x.position.y, x.position.z)
                }
            })
        }
    }
    if (message == '他人瞬移至自己位置') {
        let options = []
        world.querySelectorAll('player').forEach((x) => {
            options.push(x.player.name)
        })
        const e = await entity.player.dialog({
            type: 'select',
            title: '他人瞬移至自己位置',
            content: '你想让谁瞬移至自己位置？',
            options: options
        })
        if (e) {
            world.querySelectorAll('player').forEach((x) => {
                if (x.player.name == e.value) {
                    x.position.set(entity.position.x, entity.position.y, entity.position.z)
                }
            })
        }
    }
})
const transfer1 = world.querySelector('#key-1');
transfer1.enableInteract = true;
transfer1.interactRadius = 3;
transfer1.interactHint = '管理员通道';
transfer1.interactColor = new GameRGBColor(1, 1, 1);  // 互动提示的文字颜色

transfer1.onInteract(async ({ entity }) => {
    if (!manager.includes(entity.player.name)) {
        entity.player.directMessage('您不是管理员，无权使用！')
        return 0;
    }
    else {
        entity.player.spawnPoint = new GameVector3(56, 9, 103)
        entity.player.forceRespawn()
    }
});
const transfer2 = world.querySelector('#key-2');
transfer2.enableInteract = true;
transfer2.interactRadius = 3;
transfer2.interactHint = '管理员通道';
transfer2.interactColor = new GameRGBColor(1, 1, 1);  // 互动提示的文字颜色

transfer2.onInteract(async ({ entity }) => {
    if (!manager.includes(entity.player.name)) {
        entity.player.directMessage('您不是管理员，无权使用！')
        return 0;
    }
    else {
        entity.player.spawnPoint = new GameVector3(3, 93, 112)
        entity.player.forceRespawn()
    }
});
const transfer3 = world.querySelector('#key-3');
transfer3.enableInteract = true;
transfer3.interactRadius = 3;
transfer3.interactHint = '管理员通道';
transfer3.interactColor = new GameRGBColor(1, 1, 1);  // 互动提示的文字颜色

transfer3.onInteract(async ({ entity }) => {
    if (!manager.includes(entity.player.name)) {
        entity.player.directMessage('您不是管理员，无权使用！')
        return 0;
    }
    else {
        const sel = await entity.player.dialog({
            type: GameDialogType.SELECT,
            title: transfer3.id,
            content: `尊敬的${entity.player.name}——管理员,您好`,
            options: ['出', '入']
        })
        if (sel) {
            if (sel.value == '入') {
                entity.player.spawnPoint = new GameVector3(2, 111, 114)
                entity.player.forceRespawn()
            }
            else {
                entity.player.spawnPoint = new GameVector3(2, 111, 118)
                entity.player.forceRespawn()
            }
        }
    }
});
const board1 = world.querySelector('#特别-控制面板-1');
board1.enableInteract = true;
board1.interactRadius = 6;
board1.interactHint = '新手指南';
board1.interactColor = new GameRGBColor(1, 1, 1);  // 互动提示的文字颜色

board1.onInteract(async ({ entity }) => {
    var _tutorial = entity.player.dialog({
        type: GameDialogType.TEXT,
        tlitle: '系统1号中心-ADF32000bxd',
        content: `尊敬的玩家${entity.player.name}，这是教程! 欢迎来到${world.projectName}！(点击提示框翻页)`
    });
    _tutorial = entity.player.dialog({
        type: GameDialogType.TEXT,
        tlitle: '系统1号中心-ADF32000bxd',
        content: '初始的时候你拥有三辆车：面包车、货车、卡车和跑车。（驾驶车辆请按右键）'
    });
    _tutorial = entity.player.dialog({
        type: GameDialogType.TEXT,
        tlitle: '系统1号中心-ADF32000bxd',
        content: '货车体型较大，但速度较慢，容易上手；'
    });
    _tutorial = entity.player.dialog({
        type: GameDialogType.TEXT,
        tlitle: '系统1号中心-ADF32000bxd',
        content: '面包车体型较小，速度更快，适合开车更成熟的人使用；'
    });
    _tutorial = entity.player.dialog({
        type: GameDialogType.TEXT,
        tlitle: '系统1号中心-ADF32000bxd',
        content: '跑车体型最大（模型问题），速度也最快，适合老司机上手~'
    });
    _tutorial = entity.player.dialog({
        type: GameDialogType.TEXT,
        tlitle: '系统1号中心-ADF32000bxd',
        content: '赛道上有黄色标志桶、红色标志桶和绿色标志桶，分别有不同的作用：'
    });
    _tutorial = entity.player.dialog({
        type: GameDialogType.TEXT,
        tlitle: '系统1号中心-ADF32000bxd',
        content: '红色标志桶碰到扣的血较少，黄色相对偏多，绿色标志桶起引导作用，碰到不扣血'
    });
    _tutorial = entity.player.dialog({
        type: GameDialogType.TEXT,
        tlitle: '系统1号中心-ADF32000bxd',
        content: '希望你玩的开心！加油，冲过终点线！'
    });
});
async function yd() {
    const i = []
    const t = []
    const e = []
    const m = []
    for (var x = 0; x < 34; x++) {
        for (var z = 109; z < 127; z++) {
            for (var y = 92; y < 127; y++) {
                if (voxels.getVoxel(x, y, z) != 0) {
                    i.push(x)
                    t.push(y)
                    e.push(z)
                    m.push(voxels.getVoxel(x, y, z))
                    voxels.setVoxel(x, y, z, '')
                }
            }
        }
    }
    for (var n = 0; n <= 80; n++) {
        for (var a = 0; a < i.length; a++) {
            voxels.setVoxel(i[a] + n, t[a], e[a], '')
        }
        await sleep(1)
        for (var a = 0; a < i.length; a++) {
            voxels.setVoxel(i[a] + n + 1, t[a], e[a], m[a])
        }
        await sleep(500)
    }
    //分割线
    for (var n = 0; n <= 80; n++) {
        for (var a = 0; a < i.length; a++) {
            voxels.setVoxel(i[a] + 80 - n, t[a], e[a], '')
        }
        await sleep(1)
        for (var a = 0; a < i.length; a++) {
            voxels.setVoxel(i[a] + 80 - n - 1, t[a], e[a], m[a])
        }
        await sleep(500)
    }
}

```
