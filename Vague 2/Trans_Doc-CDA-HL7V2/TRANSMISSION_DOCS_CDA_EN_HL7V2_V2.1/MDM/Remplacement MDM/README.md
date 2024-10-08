# Remplacement  :  Messsages MDM  "volet de "Transmission de document(s) CDA en HL7v2" 

## Description
Vous trouverez sur cette page un exemple de message HL7v2.6 MDM correspondant à une demande de remplacement du CR d'imagerie médicale transmis auparavant. 
- le message MDM contient la nouvelle version du CR (version 2) sur lequel les niveaux de confidentialité ont changé : le CR est passé de l'état invisible à l'état visible au patient et à ses représentants légaux.
En conséquence, la métadonnée MODIF_CONF_CODE prend la valeur "Y" pour indiquer une modification des niveaux de confidentialité.
- le remplacement/mise à jour des métadonnées du CR est publié vers le DMP et envoyé au Dr Adam Hoda par MSS.
- Au niveau du message MDM, la demande de remplacement/maj métadonnées est indiquée par la valeur de l'OBX-11 ("C")

## Contenu
| Fichier   | Description          |
| :--------------- |:---------------|
| **CR_Radio_CDAN1_v2.XML**  |   Le document CR_Radio_CDAN1_v2.XML au format CDA N1 (nouvelle version)     | 
| **message_MDM_CR_Radio_RPLC_N1.er7**  |   Le message message_MDM_CR_Radio_RPLC_N1.er7 qui permet de transmettre la demande de remplacement du CR    | 
| **ack.er7**  |   L'acquittement technique du message HL7    | 

