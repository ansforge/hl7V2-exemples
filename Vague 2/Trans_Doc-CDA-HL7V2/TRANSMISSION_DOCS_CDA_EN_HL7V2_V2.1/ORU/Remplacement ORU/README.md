# Remplacement  :  Messsages ORU  "volet de "Transmission de document(s) CDA en HL7v2" 

## Description
Vous trouverez sur cette page un exemple de remplacement du CR de biologie transmis précédemment.
Ce répertoire contient :
- le CR en version 2 (nouvelle version du document transmis auparavant). Le lien avec la version précédente est indiqué au niveau de la balise relatedDocument dans le CDA. Dans cette nouvelle version de CR, le nom du préleveur a été modifié (Beeler en Beler), la valeur des protéïnes est passée de 75g/l à 80g/l.
- le message HL7 message_ORU_CR_Bio_RPLC_N3_SEGUR.hl7


Les documents sont envoyés au DMP et par MSS à la patiente et au Dr Adam Hoda pour remplacement des versions précédentes. Un segment PRT permet de préciser l'adresse mail sur laquelle la patiente peut le cas échéant répondre au mail reçu.
Aucun accusé de réception DMP/MSS ou accusé de lecture MSS n'est demandé.

## Contenu
| Fichier   | Description          |
| :--------------- |:---------------|
| **SEGUR_CR_Bio_CDA_Niv3_v2.xml**  |   Le document SEGUR_CR_Bio_CDA_Niv3_v2.xml au format CDA N3 (nouvelle version)     | 
| **message_ORU_CR_Bio_RPLC_N3_SEGUR.hl7**  |   Le message message_MDM_CR_Radio_RPLC_N1.er7 qui permet de transmettre la demande de remplacement du CR    | 

