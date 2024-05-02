bien venue dans un service palworld serveur dockers.
====================================================

Lien diver
----------
Lien Docker: https://hub.docker.com/r/ludix0/palworld /n
Lien des parametrages serveur: https://tech.palworldgame.com/category/settings-and-operations

docker compose
--------------

Ne pas toucher a la deuxiemme partie des ports.
Il est conseiler de rajhouter dans les arguments de rajouter "-useperfthreads -NoAsyncLoadingThread -UseMultithreadForDS".

```
services:
   palworld:
      image: ludix0/palworld:latest
      restart: unless-stopped
      container_name: palworld
      environment:
          # ajouter des arguments 
        - Arguments="-useperfthreads -NoAsyncLoadingThread -UseMultithreadForDS"
        - Difficulty=None
        - DayTimeSpeedRate=1.000000
        - NightTimeSpeedRate=1.000000
        - ExpRate=1.000000
        - PalCaptureRate=1.000000
        - PalSpawnNumRate=1.000000
        - PalDamageRateAttack=1.000000
        - PalDamageRateDefense=1.000000
        - PlayerDamageRateAttack=1.000000
        - PlayerDamageRateDefense=1.000000
        - PlayerStomachDecreaceRate=1.000000
        - PlayerStaminaDecreaceRate=1.000000
        - PlayerAutoHPRegeneRate=1.000000
        - PlayerAutoHpRegeneRateInSleep=1.000000
        - PalStomachDecreaceRate=1.000000
        - PalStaminaDecreaceRate=1.000000
        - PalAutoHPRegeneRate=1.000000
        - PalAutoHpRegeneRateInSleep=1.000000
        - BuildObjectDamageRate=1.000000
        - BuildObjectDeteriorationDamageRate=1.000000
        - CollectionDropRate=1.000000
        - CollectionObjectHpRate=1.000000
        - CollectionObjectRespawnSpeedRate=1.000000
        - EnemyDropItemRate=1.000000

          # Peine de mort
          # None : Aucun drop - Item : Drop tous les objets sauf l'équipement
          # ItemAndEquipment : Drop tous les objets 
          # All : Drop tous les objets et tous les amis de l'équipe
        - DeathPenalty=ItemAndEquipment
        - bEnablePlayerToPlayerDamage=False
        - bEnableFriendlyFire=False
        - bEnableInvaderEnemy=False
        - bActiveUNKO=False
        - bEnableAimAssistPad=True
        - bEnableAimAssistKeyboard=False
        - DropItemMaxNum=3000
        - DropItemMaxNum_UNKO=100
        - BaseCampMaxNum=128
        - BaseCampWorkerMaxNum=15
        - DropItemAliveMaxHours=1.000000
        - bAutoResetGuildNoOnlinePlayers=False
        - AutoResetGuildTimeNoOnlinePlayers=72.000000
        - GuildPlayerMaxNum=20
        - PalEggDefaultHatchingTime=72.000000
        - WorkSpeedRate=1.000000
        - bIsMultiplay=False
        - bIsPvP=False
        - bCanPickupOtherGuildDeathPenaltyDrop=False
        - bEnableNonLoginPenalty=True
        - bEnableFastTravel=True
        - bIsStartLocationSelectByMap=True
        - bExistPlayerAfterLogout=False
        - bEnableDefenseOtherGuildPlayer=False
        - CoopPlayerMaxNum=4
        - ServerPlayerMaxNum=4
        - ServerName=Ludix_palworld_FR
        - ServerDescription=
        - AdminPassword=
        - ServerPassword=
        - PublicIP=
        - RCONEnabled=False
        - Region=
        - bUseAuth=True
        - BanListURL="https://api.palworldgame.com/api/banlist.txt"
        - RESTAPIEnabled=False
        - bShowPlayerList=False
        - AllowConnectPlatform=Steam
        - bIsUseBackupSaveData=True

      volumes: 
        - $HOME/volumes/palworld/data:/server
      ports:
        - 7776:8211/udp
        - 7775:8212/udp
```

