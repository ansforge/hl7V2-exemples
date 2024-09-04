# Exemples de messsages ORU  "volet de "Transmission de document(s) CDA en HL7v2" 

## Description
Vous trouverez sur cette page des exemples de messages ORU en HL7v2.5 dans le contexte du volet "Transmission de document(s) CDA en HL7v2, vague2".
| Repertoire  | Description          |
| :--------------- |:---------------|
| **Transmission initiale ORU**  |   Contient un exemple de message HL7v2 ORU qui contient un CR de biologie au format CDA N1 et le même contenu clinique au format CDA N3. Il s'agit de deux documents différents au même contenu clinique mais au format différent transmis par le Créateur au Gestionnaire pour la première fois.      | 
|  **Remplacement ORU** |   Contient un exemple de message HL7v2 ORU qui contient une nouvelle version des 2 documents CDA N1 et CDA N3 précédemment transmis. le champ OBX-11 des segments OBX portant les nouvelles versions de document prend la valeur C indiquant ainsi une demande de remplacement des documents initiaux. Le lien avec la version précédente du document est indiqué par l'élément relatedDocument au niveau du CDA.     | 
|  **Suppression ORU** |  Contient un exemple de message HL7v2 ORU qui contient la dernière version des documents à supprimer. le champ OBX-11 des segments OBX portant les documents prend la valeur D pour indiquer une demande de suppression.  | 

 
## Integration avec l'environnement de test du DMP
Si vous souhaiter réaliser un test d'integration avec l'environnement de DMP de test, vous allez devoir effectuer des modifications sur les exemples mis à disposition.

### Patient
Le patient utilisé dans les exemples est le patient "PAT-TROIS DOMINIQUE". 
Ce patient est connu du DMP de test. Il n'y a donc pas de modification à faire dans le document CDA encodé en base64 et le segment PID des messages. 

### identifiant du document  CDA
L'identifiant du document CDA  se retrouve dans l'élement **ID** du document CDA.

Exemple pour un document CDA : 
```XML
<id root="1.2.250.2345.3245.13.58132">
```
#### Instruction

1. Décoder le document CDA
Pour cela il faut récuper le document CDA qui est dans le champ **OBX-5.4** 
2. Générer un nouvelle identifiant de document
3. Remplacer l'identifiant du document CDA
4. Re-encoder en base 64 le document CDA
5. Remplacer le champ **OBX-5.4** par le nouveau document CDA

#### Cas du remplacement de document
Dans le cas d'un remplacement de document, on retrouve l'identifiant du document à remplacer dans l'élement **relatedDocument" qui correspond à l'identifiant du document remplacé.

Exemple pour un document CDA : 
```XML
<relatedDocument typeCode="RPLC">
<parentDocument>
<id root="1.2.250.2345.3245.13.58132"/>
</parentDocument>
</relatedDocument
```
#### Instruction

Dans ce cas, il vous faudra modifier l'identifiant du document remplacé dans le document CDA.

### Synthése des modifications à effectuer
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







