Un exemple de suppression des deux CR de biologie transmis précédemment. Ce répertoire contient :
- Les 2 CR en version 2 (documents transmis dans l'étape précédente).
- Le message HL7 message_ORU_CR_Bio_DEL_N1_N3.er7 et le message message_ORU_CR_Bio_DEL_N1_Base64_N3_Base64.er7 (même message mais avec les documents en Base64)
- Le message d'acquittement technique

Les documents sont envoyés au DMP et par MSS à la patiente et au Dr Adam Hoda pour suppression. Aucun accusé de réception DMP/MSS ou accusé de lecture MSS n'est demandé.

# Suppression  :  Messsages ORU  "volet de "Transmission de document(s) CDA en HL7v2" 

## Description
Vous trouverez sur ce répertoire un exemple de message HL7v2.5 ORU correspondant à une demande de suppression du CR d'imagerie médicale transmis à l'étape précédente:

- le message ORU contient la dernière version du CR à supprimer.
- la demande de suppression du CR est publiée vers le DMP et envoyéé au Dr Adam Hoda par MSS.
- Au niveau du message ORU, la demande de suppression est indiquée par la valeur de l'OBX-11 ("D")

## Contenu
| Fichier   | Description          |
| :--------------- |:---------------|
| **SEGUR_CR_Bio_CDA_Niv3_v2.xml**  |   La version du CR d'imagerie à supprimer, SEGUR_CR_Bio_CDA_Niv3_v2.xml  | 
| **message_ORU_CR_Bio_DEL_N3_SEGUR.hl7**  |   Le message HL7 message_ORU_CR_Bio_DEL_N3_SEGUR.hl7 portant le document à supprimer | 
