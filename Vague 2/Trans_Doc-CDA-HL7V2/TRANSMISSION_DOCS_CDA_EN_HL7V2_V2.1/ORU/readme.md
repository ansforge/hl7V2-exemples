# Exemples de messages ORU  "volet de "Transmission de document(s) CDA en HL7v2" 

## Description
Vous trouverez sur cette page des exemples de messages ORU en HL7v2.5 dans le contexte du volet "Transmission de document(s) CDA en HL7v2, vague2".
| Repertoire  | Description          |
| :--------------- |:---------------|
| **Transmission initiale ORU**  |   Contient un exemple de message HL7v2 ORU qui contient un CR de biologie au format CDA N3 transmis par le Créateur au Gestionnaire pour la première fois.      | 
|  **Remplacement ORU** |   Contient un exemple de message HL7v2 ORU qui contient une nouvelle version du document CDA N3 précédemment transmis. le champ OBX-11 des segments OBX portant les nouvelles versions de document prend la valeur C indiquant ainsi une demande de remplacement des documents initiaux. Le lien avec la version précédente du document est indiqué par l'élément relatedDocument au niveau du CDA.     | 
|  **Suppression ORU** |  Contient un exemple de message HL7v2 ORU qui contient la dernière version du document à supprimer. le champ OBX-11 du segment OBX portant le document prend la valeur D pour indiquer une demande de suppression.  | 

 
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
Pour cela il faut récuperer le document CDA qui est dans le champ **OBX-5.4** 
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
</relatedDocument>
```
#### Instruction

Dans ce cas, il vous faudra modifier l'identifiant du document remplacé dans le document CDA.

### éléments à modifier pour contruire le VIHF

#### message HL7v2
Afin de construire le VIHF et pouvoir s'autentifier pour intégrer le document dans le DMP il faut modifier dans le message HL7v2 le segment PRT ayant pour valeur PRT-4 = ‘SB^Send by^participation’:

* PRT-5.1: Identifiant du professionnel qui fait la demande de traitement sur le(s) document(s)
* PRT-5.2: Nom d’exercice du professionnel expéditeur
* PRT-5.3: Prénom d’exercice du professionnel expéditeur
* PRT-8.1: Nom de l’organisation
* PRT-8.7: Type d’identifiant de l’organisation (selon le type de connexion)
* PRT-8.10:  Identifiant de l’organisation destinataire du document

Ces éléments doivent correspondre au certificat de l'éditeur pour la structure identifiée.

#### metadata XDS

En cohérence avec les éléments à modifier dans le message HL7v2, il vous faudra modifier :

* authorInstitution: structure émettrice du lot de soumission ou de l'auteur pour une fiche
* authorPerson: personne physique (auteur) ou le système émetteur du lot de soumission

Mais également :

* authorRole: le rôle joué par l’auteur vis-à-vis du patient lors de la constitution du lot de soumission ou lors de la création du document (fiche)
* authorSpecialty: profession éventuellement associée au savoir-faire de l’auteur du lot de soumission pour un auteur professionnel caractérisé par sa profession ou la profession associée au genre d’activité de l’auteur du lot de soumission ou de la fiche pour un auteur professionnel caractérisé par son rôle

#### CDA

Pour une mise en cohérence en lien aux éléments cités précédemment, pour pourrez modifié également dans le document CDA :

* author/assignedAuthor/representedOrganization
* author/assignedAuthor
* authorfunctionCode@displayName
* author/assignedAuthor/code

Pour cela il vous faudra :

1. Décoder le document CDA
Pour cela il faut récuperer le document CDA qui est dans le champ **OBX-5.4** 
2. Apporter les modifications
3. Re-encoder en base 64 le document CDA
4. Remplacer le champ **OBX-5.4** par le nouveau document CDA

### Synthése des modifications à effectuer
| Segment  | Champs          | Description | Instruction |
| :--------------- |:---------------| :-----:| :-----|
| MSH  |   MSH-3        |  Application émettrice  | |
| MSH  | MSH-4          |   Organisation émettrice  |  |
| MSH  | MSH-5          |    Application réceptrice  | |
| MSH  | MSH-6          |   Organisation réceptrice | |
| MSH  | MSH-7          |    Date/time du message | |
| MSH  | MSH-10          |   Identifiant du message  | |
| PRT | PRT-5.1          | Identifiant du professionnel qui fait la demande de traitement sur le(s) document(s)   | contexte : voir [Integration avec l'environnement de test du DMP](https://github.com/ansforge/hl7V2-exemples/tree/main/Vague%202/Trans_Doc-CDA-HL7V2/TRANSMISSION_DOCS_CDA_EN_HL7V2_V2.1/MDM#integration-avec-lenvironnement-de-test-du-dmp) |
| PRT | PRT-5.2          | Nom d’exercice du professionnel expéditeur   | contexte : voir [Integration avec l'environnement de test du DMP](https://github.com/ansforge/hl7V2-exemples/tree/main/Vague%202/Trans_Doc-CDA-HL7V2/TRANSMISSION_DOCS_CDA_EN_HL7V2_V2.1/MDM#integration-avec-lenvironnement-de-test-du-dmp) |
| PRT | PRT-5.3          | Prénom d’exercice du professionnel expéditeur   | contexte : voir [Integration avec l'environnement de test du DMP](https://github.com/ansforge/hl7V2-exemples/tree/main/Vague%202/Trans_Doc-CDA-HL7V2/TRANSMISSION_DOCS_CDA_EN_HL7V2_V2.1/MDM#integration-avec-lenvironnement-de-test-du-dmp) |
| PRT  | PRT-8.1         |   Nom de l’organisation   | contexte : voir [Integration avec l'environnement de test du DMP](https://github.com/ansforge/hl7V2-exemples/tree/main/Vague%202/Trans_Doc-CDA-HL7V2/TRANSMISSION_DOCS_CDA_EN_HL7V2_V2.1/MDM#integration-avec-lenvironnement-de-test-du-dmp) |
| PRT  | PRT-8.7         |   Type d’identifiant de l’organisation   | contexte : voir [Integration avec l'environnement de test du DMP](https://github.com/ansforge/hl7V2-exemples/tree/main/Vague%202/Trans_Doc-CDA-HL7V2/TRANSMISSION_DOCS_CDA_EN_HL7V2_V2.1/MDM#integration-avec-lenvironnement-de-test-du-dmp) |
| PRT  | PRT-8.10        |  Identifiant de l’organisation à l’origine de la demande de traitement sur le(s) document(s)   |  Contexte : voir [Integration avec l'environnement de test du DMP](https://github.com/ansforge/hl7V2-exemples/tree/main/Vague%202/Trans_Doc-CDA-HL7V2/TRANSMISSION_DOCS_CDA_EN_HL7V2_V2.1/MDM#integration-avec-lenvironnement-de-test-du-dmp)  |
| OBX  | OBX-5.4         |  Document CDA encodé en base 64    | |







