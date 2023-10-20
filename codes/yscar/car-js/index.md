## car.js
```javascript
world.onPress(async ({ entity, button }) => {
    if (button == GameButtonType.ACTION1) {
        if (entity.player.dead) return
        const select1 = await entity.player.dialog({
            type: GameDialogType.SELECT,
            title: '菜单',
            content: '请选择操作',
            options: ['开车', '选择音乐', '下车']
        })
        if (select1) {
            if (select1.value == '开车') {
                const select = await entity.player.dialog({
                    type: GameDialogType.SELECT,
                    title: '菜单',
                    content: '请选择车辆',
                    options: ['面包车', '货车', '跑车', '卡车', '法拉利F1', '无名红色赛车', '无名白色赛车']
                })
                if (select) {
                    if (select.value == '面包车') {

                        entity.maxHp = 10
                        entity.enableDamage = true
                        entity.player.canFly = false;//false;
                        entity.player.invisible = true;
                        entity.player.jumpPower = false
                        entity.mesh = world.querySelector('#轿车').mesh
                        entity.meshOrientation = new GameQuaternion(0, 1, 0, 0).rotateY(-Math.PI / 2)
                        entity.player.runSpeed = 2.4
                        entity.player.walkSpeed = entity.player.runSpeed
                        entity.meshScale = new GameVector3(1 / 32, 1 / 32, 1 / 32);
                        entity.player.runAcceleration = 0.71
                        entity.player.spawnPoint = new GameVector3(5, 10, 115) //过会儿试下这里
                        entity.player.forceRespawn()
                        world.onVoxelContact(async ({ entity, voxel }) => {
                            if (voxel == 185) {
                                entity.hurt(1)
                            }
                            else if (voxel == 189) {
                                entity.hurt(3)
                            }
                        })
                    }

                    else if (select.value == '货车') {

                        entity.maxHp = 20//20
                        entity.enableDamage = true
                        entity.player.canFly = false;
                        entity.player.jumpPower = false
                        entity.player.invisible = true;
                        entity.mesh = world.querySelector('#货车').mesh
                        entity.meshOrientation = new GameQuaternion(0, 1, 0, 0).rotateY(Math.PI)
                        entity.player.runSpeed = 1.6
                        entity.player.walkSpeed = entity.player.runSpeed
                        entity.meshScale = new GameVector3(1 / 32, 1 / 32, 1 / 32);
                        entity.player.runAcceleration = 0.7
                        entity.player.spawnPoint = new GameVector3(5, 10, 115) //过会儿试下这里
                        entity.player.forceRespawn()
                        world.onVoxelContact(async ({ entity, voxel }) => {
                            if (voxel == 185) {
                                entity.hurt(1)
                            }
                            else if (voxel == 189) {
                                entity.hurt(3)
                            }
                        })
                    }
                    else if (select.value == '跑车') {

                        entity.maxHp = 10
                        entity.enableDamage = true
                        entity.player.canFly = false;
                        entity.player.jumpPower = false
                        entity.player.invisible = true;
                        entity.mesh = world.querySelector('#跑车-1').mesh
                        entity.meshOrientation = new GameQuaternion(0, 1, 0, 0).rotateY(-Math.PI / 2)
                        entity.player.runSpeed = 3.2
                        entity.player.walkSpeed = entity.player.runSpeed
                        entity.meshScale = new GameVector3(1 / 32, 1 / 32, 1 / 32);
                        entity.player.runAcceleration = 0.8
                        entity.player.spawnPoint = new GameVector3(5, 10, 115) //过会儿试下这里
                        entity.player.forceRespawn()
                        world.onVoxelContact(async ({ entity, voxel }) => {
                            if (voxel == 185) {
                                entity.hurt(1)
                            }
                            else if (voxel == 189) {
                                entity.hurt(3)
                            }
                        })

                    }
                    else if (select.value == '卡车') {

                        entity.maxHp = 15
                        entity.enableDamage = true
                        entity.player.canFly = false;
                        entity.player.jumpPower = false
                        entity.player.invisible = true;
                        entity.mesh = world.querySelector('#擎天柱卡车-1').mesh
                        entity.meshOrientation = new GameQuaternion(0, 1, 0, 0).rotateY(-Math.PI / 2)
                        entity.player.runSpeed = 5
                        entity.player.walkSpeed = entity.player.runSpeed
                        entity.meshScale = new GameVector3(1 / 128, 1 / 128, 1 / 128);
                        entity.player.runAcceleration = 2.5
                        entity.player.spawnPoint = new GameVector3(5, 10, 115) //过会儿试下这里
                        entity.player.forceRespawn()
                        world.onVoxelContact(async ({ entity, voxel }) => {
                            if (voxel == 185) {
                                entity.hurt(1)
                            }
                            else if (voxel == 189) {
                                entity.hurt(3)
                            }
                        })
                    }
                    else if (select.value == '法拉利F1') {

                        entity.maxHp = 35
                        entity.enableDamage = true
                        entity.player.canFly = false;
                        entity.player.jumpPower = false
                        entity.player.invisible = true;
                        entity.mesh = world.querySelector('#法拉利 F1-1').mesh
                        entity.meshOrientation = new GameQuaternion(0, 1, 0, 0).rotateY(-Math.PI / 2)
                        entity.player.runSpeed = 10
                        entity.player.walkSpeed = entity.player.runSpeed
                        entity.meshScale = new GameVector3(1 / 192, 1 / 192, 1 / 192);
                        entity.player.runAcceleration = 2.5
                        entity.player.spawnPoint = new GameVector3(5, 10, 115) //过会儿试下这里
                        entity.player.forceRespawn()
                        world.onVoxelContact(async ({ entity, voxel }) => {
                            if (voxel == 185) {
                                entity.hurt(1)
                            }
                            else if (voxel == 189) {
                                entity.hurt(3)
                            }
                        })
                    }
                    else if (select.value == '无名红色赛车') {

                        entity.maxHp = 20
                        entity.enableDamage = true
                        entity.player.canFly = false;
                        entity.player.jumpPower = false
                        entity.player.invisible = true;
                        entity.mesh = world.querySelector('#一个赛车-1').mesh
                        entity.meshOrientation = new GameQuaternion(0, 1, 0, 0).rotateY(-Math.PI / 2)
                        entity.player.runSpeed = 5
                        entity.player.walkSpeed = entity.player.runSpeed
                        entity.meshScale = new GameVector3(1 / 32, 1 / 32, 1 / 32);
                        entity.player.runAcceleration = 2.5
                        entity.player.spawnPoint = new GameVector3(5, 10, 115) //过会儿试下这里
                        entity.player.forceRespawn()
                        world.onVoxelContact(async ({ entity, voxel }) => {
                            if (voxel == 185) {
                                entity.hurt(1)
                            }
                            else if (voxel == 189) {
                                entity.hurt(3)
                            }
                        })
                    }
                    else if (select.value == '无名白色赛车') {

                        entity.maxHp = 20
                        entity.enableDamage = true
                        entity.player.canFly = false;
                        entity.player.jumpPower = false
                        entity.player.invisible = true;
                        entity.mesh = world.querySelector('#白色赛车-1').mesh
                        entity.meshOrientation = new GameQuaternion(0, 1, 0, 0).rotateY(-Math.PI / 2)
                        entity.player.runSpeed = 5
                        entity.player.walkSpeed = entity.player.runSpeed
                        entity.meshScale = new GameVector3(1 / 32, 1 / 32, 1 / 32);
                        entity.player.runAcceleration = 2.5
                        entity.player.spawnPoint = new GameVector3(5, 10, 115) //过会儿试下这里
                        entity.player.forceRespawn()
                        world.onVoxelContact(async ({ entity, voxel }) => {
                            if (voxel == 185) {
                                entity.hurt(1)
                            }
                            else if (voxel == 189) {
                                entity.hurt(3)
                            }
                        })
                    }
                }
            }
            if (select1.value == '下车') {

                entity.player.canFly = true;
                entity.enableDamage = false
                entity.player.invisible = false;
                entity.player.jumpPower = true
                entity.mesh = entity.originPlayerMesh
                entity.player.runSpeed = 0.4 //默认值
                entity.player.walkSpeed = 0.22 //默认值
                entity.player.runAcceleration = 0.35   //控制玩家加速度
                entity.player.spawnPoint = new GameVector3(22, 94, 119)
                entity.player.forceRespawn()
                entity.player.directMessage('下车成功');

            }
        }
    }
})
world.onDie(async ({ entity }) => {
    if (!entity.isPlayer) return
    entity.player.canFly = true;
    entity.player.invisible = false;
    entity.player.jumpPower = true
    entity.mesh = entity.originPlayerMesh
    world.say(`${entity.player.name}撞死在方块上；提示：行车不规范，亲人两行泪`)
    entity.player.directMessage('5秒后复活')
    await sleep(5000)
    entity.hp = Infinity
    entity.maxHp = Infinity
    entity.player.spawnPoint = new GameVector3(22, 94, 119)
    entity.player.forceRespawn()
    entity.player.runSpeed = 0.4 //默认值
    entity.player.walkSpeed = 0.22 //默认值
    entity.player.runAcceleration = 0.35   //控制玩家加速度
})
```
