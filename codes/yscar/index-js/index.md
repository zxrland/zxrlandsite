## index.js
```javascript
console.clear()
require('./time-sun-gui.js')
require('./car.js')
require('./manager.js')
require('./second-manager.js')
require('./other.js')
require('./racer.js')
//黄色条纹：障碍桶，碰到扣三滴血    红色条纹：边缘桶，碰到扣1滴血  绿色条纹：引导桶，碰到不扣血
//面包车：速度2.4  血量10  货车：速度1.6  血量20  跑车：速度3.2  血量5 （难度逐渐增高）




world.onPlayerJoin(({ entity }) => {
    entity.player.directMessage('欢迎来到赛车的世界~~')
    world.addCollisionFilter('player', 'player')
    entity.player.canFly = true;
    world.ambientSound.sample = 'audio/Wolves-Selena-Gomez_marshmello(bgm).mp3';//改变地图背景音乐，从地图运行开始循环播放。
});

```
