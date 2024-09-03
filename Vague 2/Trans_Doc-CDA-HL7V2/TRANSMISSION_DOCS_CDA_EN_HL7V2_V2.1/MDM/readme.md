# Exemple de messsages MDM  "volet de "Transmission de document(s) CDA en HL7v2" 

## Description
Vous trouverez sur cette page des exemples de messages MDM en HL7v2.6 dans le contexte du volet "Transmission de document(s) CDA en HL7v2, vague2".
- le répertoire **Transmission initiale MDM** :
  - contient un exemple de message HL7v2 MDM qui contient un CR d'imagerie médicale au format CDA N1 transmis au GESTIONNAIRE pour la première fois.
- le répertoire **Remplacement MDM** :
  - contient un exemple de message HL7v2 MDM qui contient une nouvelle version du document CDA N1 précédemment transmis. le champ OBX-11 du segment OBX portant la nouvelle version de document prend la valeur C indiquant ainsi une demande de remplacement du document initial. le lien avec la version précédente du document est indiqué par l'élément relatedDocument au niveau du CDA.
- le répertoire **Suppression MDM**  :
  - contient un exemple de message HL7v2 MDM qui contient la dernière version d'un document à supprimer. le champ OBX-11 du segment OBX portant le document prend la valeur D pour indiquer une demande de suppression.
 
## Integration avec l'environnement de test du DMP
Dans le cas d'un test d'integration avec l'envrionnement de DMP de test, vous devez modifier des valeurs de segments des messages HLV2.


### Tableau des modifications
| Segment  | Champs          | Description | Instruction |
| :--------------- |:---------------| :-----:| :-----|
| MSH  |   MSH-3        |  Application émettrice  | |
| MSH  | MSH-4          |   Organisation émettrice  |  |
| MSH  | MSH-5          |    Application réceptrice  | |
| MSH  | MSH-6          |   Organisation réceptrice | |
| MSH  | MSH-7          |    Date/time du message | |
| MSH  | MSH-10          |   Identifiant du message  | |
| PRT  | PRT-8.1         |   Nom de l’organisation   | |
| PRT  | PRT-8.10        |  Identifiant de l’organisation destinataire du document   |  FINESS Geographique correspondant au certicat utilisé pour l'alimentation |
| OBX  | OBX-5.4         |  Document CDA encodé en base 64    | |






