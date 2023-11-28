Vous trouverez sur cette page un exemple de message HL7v2.6 MDM correspondant à une demande de suppression du CR d'imagerie médicale transmis à l'étape précédente. 
le message MDM contient la dernière version du CR à supprimer.

la demande de suppression du CR est publiée vers le DMP et envoyéé au Dr Adam Hoda par MSS. Au niveau du message MDM, la demande de suppression est indiquée par la valeur de l'OBX-11 ("D")

Suppression du CR d'imagerie:
- la version du CR d'imagerie à supprimer, CR_Radio_CDAN1_v2.XML,
- le message HL7 message_MDM_CR_Radio_DEL_N1.er7 portant le document à supprimer,
- l'accusé de réception technique du message HL7, ack.er7.
