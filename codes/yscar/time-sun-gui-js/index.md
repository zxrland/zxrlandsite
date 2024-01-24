## time-sun-gui.js
```javascript
//moment.js源代码可在https://momentjs.com下载
const moment = require('./moment.js')

var utcPlus8Hours = null





world.onPlayerJoin(({ entity }) => {
    gui.init(entity, {
        "panel": {
            display: true,
            data: `<dialog width="300" percentHeight="100" top="60" right="20" id="">
            <group percentWidth="100" height="120" y="0">
                <label text="玩家血量" height="35" y="5"  x="10"  percentWidth="100" color="#fff" fontSize="20"></label>
                <label text="" height="25" y="35" x="10" percentWidth="100" color="#fff" id="pointshowx"></label>
            </group>
            <group percentWidth="100" height="120" y="0">
                <label text="qq群号：774269122" height="35" y="50"  x="10"  percentWidth="100" color="#fff" fontSize="20"></label>
            </group>
            <group percentWidth="100" height="120" y="0">
                <label text="" height="35" y="80"  x="10" percentWidth="100" color="#fff" id="timehms" fontSize="20"></label>
            </group>
        </dialog>`
        }
    })
    world.onTick(({ tick }) => {
        utcPlus8Hours = moment().utcOffset("+08:00").get('hour')
        if (utcPlus8Hours == 0) {
            world.sunPhase = 1
        }
        else if (utcPlus8Hours == 1) {
            world.sunPhase = 0.96
        }
        else if (utcPlus8Hours == 2) {
            world.sunPhase = 0.92
        }
        else if (utcPlus8Hours == 3) {
            world.sunPhase = 0.88
        }
        else if (utcPlus8Hours == 4) {
            world.sunPhase = 0.76
        }
        else if (utcPlus8Hours == 5) {
            world.sunPhase = 0.72
        }
        else if (utcPlus8Hours == 6) {
            world.sunPhase = 0.68
        }
        else if (utcPlus8Hours == 7) {
            world.sunPhase = 0.64
        }
        else if (utcPlus8Hours == 8) {
            world.sunPhase = 0.6
        }
        else if (utcPlus8Hours == 9) {
            world.sunPhase = 0.56
        }
        else if (utcPlus8Hours == 10) {
            world.sunPhase = 0.52
        }
        else if (utcPlus8Hours == 11) {
            world.sunPhase = 0.48
        }
        else if (utcPlus8Hours == 12) {
            world.sunPhase = 0.44
        }
        else if (utcPlus8Hours == 13) {
            world.sunPhase = 0.48
        }
        else if (utcPlus8Hours == 14) {
            world.sunPhase = 0.52
        }
        else if (utcPlus8Hours == 15) {
            world.sunPhase = 0.56
        }
        else if (utcPlus8Hours == 16) {
            world.sunPhase = 0.6
        }
        else if (utcPlus8Hours == 17) {
            world.sunPhase = 0.64
        }
        else if (utcPlus8Hours == 18) {
            world.sunPhase = 0.68
        }
        else if (utcPlus8Hours == 19) {
            world.sunPhase = 0.72
        }
        else if (utcPlus8Hours == 20) {
            world.sunPhase = 0.76
        }
        else if (utcPlus8Hours == 21) {
            world.sunPhase = 0.8
        }
        else if (utcPlus8Hours == 22) {
            world.sunPhase = 0.84
        }
        else if (utcPlus8Hours == 23) {
            world.sunPhase = 0.88
        }
        gui.setAttribute(entity, "#pointshowx", "text", `${~~entity.maxHp}/${~~entity.hp}`);
        gui.setAttribute(entity, "#timehms", "text", `目前时间：${moment().utcOffset("+08:00").format('HH时mm分ss秒')}`);
    })

})
```
