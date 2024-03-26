Vous trouverez sur cette page un exemple de message HL7v2.6 MDM correspondant à une demande de suppression du CR d'imagerie médicale transmis à l'étape précédente.
Le message MDM contient la dernière version du CR à supprimer.

La demande de suppression du CR est réceptionnée par le GESTIONNAIRE (la PFI) via l'arrivée d'un courriel et est envoyée au DPI de l'hôpitalA via le message MDM. 
Au niveau du message MDM, la demande de suppression est indiquée par la valeur de l'OBX-11 ("D") et par la valeur de l'ORC-1 qui prend la valeur CA.

Suppression du CR d'imagerie:
- la version du CR d'imagerie à supprimer, CR_Radio_CDAN1_v2.XML,
- le message HL7 message_MDM__LPS_MSS_CR_Radio_DEL_N1.er7 portant le document à supprimer,
- l'accusé de réception du message HL7, ack.er7.

