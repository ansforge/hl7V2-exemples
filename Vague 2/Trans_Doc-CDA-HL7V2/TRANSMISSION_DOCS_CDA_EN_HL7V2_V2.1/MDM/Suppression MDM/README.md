# Suppression  :  Messsages MDM  "volet de "Transmission de document(s) CDA en HL7v2" 

## Description
Vous trouverez sur cette page un exemple de message HL7v2.6 MDM correspondant à une demande de suppression du CR d'imagerie médicale transmis à l'étape précédente. 
le message MDM contient la dernière version du CR à supprimer.
- la demande de suppression du CR est publiée vers le DMP et envoyéé au Dr Adam Hoda par MSS.
- Au niveau du message MDM, la demande de suppression est indiquée par la valeur de l'OBX-11 ("D")

## Contenu
| Fichier   | Description          |
| :--------------- |:---------------|
| **CR_Radio_CDAN1_v2.XML**  |   La version du CR d'imagerie à supprimer, CR_Radio_CDAN1_v2.XML  | 
| **message_MDM_CR_Radio_DEL_N1.er7**  |   Le message HL7 message_MDM_CR_Radio_DEL_N1.er7 portant le document à supprimer | 
| **ack.er7**  |   L'acquittement technique du message HL7    | 

