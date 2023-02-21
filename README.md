# sequenceur-PTT-RTS-DTR-avec-CW-retarde

Sequencer with morse delayed, ok V/UHF, but sensitive with HF
Depuis installation d'un préamplificateur d'antenne VHF avec son relais astable, et un relais bistable pour l'antenne UHF, j'utilisais le séquenceur à  PIC de F5UBZ en version bistable.

Le problème c'est que j'utilisais uniquement le PTT du micro pour activer le séquenceur!

Donc plus possible de faire du morse avec mon manipulateur, n'y de mode numérique....

Cahier des charges:

Garder le PIC 12f675 séquenceur de F5UBZ car il fonctionne correctement pour mon utilisation.

Ne pas perdre de point ou de trait lors de l'utilisation de mon paddle/pioche ou du PC via la sortie du port COM DTR (logiciel morse...)

Il a fallu réfléchir à retarder le morse avec un arduino! C'est le coeur du systeme, merci à Florian!

Pouvoir commuter le RTS du port COM pour utiliser les modes numérique (SSTV, FT8, JT65....), après les relais coaxiaux!

=> Surtout ne pas commuter le relais PTT micro en cas d'utilisation de la CW, ou des commutation DTR ou RTS!

=> Maintenir les relais actif pendant 600ms (ajustable par soft) en cas d'utilisation de la CW (c'est DH8BQA qui me la fait pensé)



voir :

https://sites.google.com/site/f8cjsradioamateur/techniques/sequenceur-ptt-drt-rts-et-keyer-cw-int%C3%A9gr%C3%A9-et-retard%C3%A9


Grosse erreur avec ce shéma, la bobine du PTT est alimenté par le régulateur 5V du CI.

Résultat, si le 24V ou 28V de la commandes des relais n'est pas allumé, le PTT peux quand même passé en émission.

J'ai donc coupé la piste qui arrive au relais PTT, et mis une résistance en volant vers le +28V de la commande des relais.
