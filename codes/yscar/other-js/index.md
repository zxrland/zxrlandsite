## other.js
```javascript
//汽油补充
const oiler = world.querySelector('#加油器-1')
oiler.enableInteract = true
oiler.interactHint = '92号汽油'
oiler.fixed = true
oiler.collides = true
oiler.gravity = false
oiler.onInteract(async ({ entity }) => {
    if (entity.player.dead) return
    entity.hp = entity.maxHp
    entity.player.directMessage('油已加满')
});


//新手教程&Q群
world.onPlayerJoin(async ({ entity }) => {
    var answer = await entity.player.dialog({
        type: GameDialogType.SELECT,
        tlitle: '系统1号中心-ADF32000bxd',
        content: '您好,请问您玩过这款游戏吗? 需要帮助吗?',
        options: ['玩过忘记了,可以给一点帮助吗?', '第一次玩,一点不会诶', '我会玩,谢谢', '管理员专用']
    });
    if (!answer || answer === null || answer === '我会玩,谢谢') {
        return;
    }
    switch (answer.index) {
        case 0:
            var _tutorial = entity.player.dialog({
                type: GameDialogType.TEXT,
                tlitle: '系统1号中心-ADF32000bxd',
                content: `尊敬的玩家${entity.player.name}，这是教程! 欢迎来到${world.projectName}！(点击提示框翻页)`
            });
            _tutorial = entity.player.dialog({
                type: GameDialogType.TEXT,
                tlitle: '系统1号中心-ADF32000bxd',
                content: '初始的时候你拥有四辆车：面包车、货车、卡车和跑车。（驾驶车辆请按右键）'
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
                content: '卡车血量最厚，速度快，适合追求速度的新手～'
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
        case 1:
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
                content: '卡车血量最厚，速度快，适合追求速度的新手～'
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
        case 3:
            var managerhelper = entity.player.dialog({
                type: GameDialogType.TEXT,
                tlitle: '系统1号中心-ADF32000bxd',
                content: `尊敬的管理员，你可以：变大、大小还原、发光、终极发光、飞行、解除飞行、还原颜色、变青、蓝、红、黄、绿、紫、黑、粉、橙、颜色还原、隐身、隐藏名字。显示名字、幽灵、取消幽灵、跳高、反光、金属感、第一人称视角、第三人称视角、下雨、停雨、下雪、停雪、起雾、停雾、取消玩家互相碰撞、允许玩家互相碰撞、瞬移至他人位置、他人瞬移至自己位置。`
            });
    }
    var qqts = entity.player.dialog({
        type: GameDialogType.TEXT,
        title: 'qq群',
        content: '原始赛车场qq群：774269122'
    })
});



```
