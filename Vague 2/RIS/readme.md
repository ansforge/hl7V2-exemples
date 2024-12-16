# Exemple de documents CDA   

## Description
Vous trouverez sur cette page des exemples de document CDA  dans le contexte du volet "Transmission de document(s) CDA en HL7v2, vague2".
| Repertoire  | Description          |
| :--------------- |:---------------|
| **Transmission initiale**  |   Contient un CR d'imagerie au format CDA      | 
|  **Remplacement** |   Contient une nouvelle version du CR d'imagerie au format CDA     | 
|  **Suppression** |  Contient la version du CR d'imagerie à supprimer  | 

 
## Integration avec l'environnement de test du DMP
Dans le cas d'un test d'integration avec l'environnement de DMP de test, vous allez devoir effectuer des modifications sur les exemples mis à disposition.

### Patient
Le patient utilisé dans les exemples est le patient "PAT-TROIS DOMINIQUE". 
Ce patient est connu du DMP de test. Il n'y a donc pas de modification à faire dans le document CDA encodé en base64 et le segment PID des messages.


### structure de l'auteur du document CDA
L'identifiant de structure de l'auteur du document CDA se retrouve  dans l'élement **author/assignedAuthor/representedOrganization/id** du document CDA.

Exemple pour un document CDA : 
```XML
<author>
<time value="20210409094914.827+0100"></time>
<assignedAuthor>
<id extension="801234564895" root="1.2.250.1.71.4.2.1"></id>
<addr nullFlavor="UNK"></addr>
<telecom nullFlavor="UNK"></telecom>
<assignedPerson>
<name>
<family qualifier="SP">Eric</family>
<given>Thomas</given>
</name>
</assignedPerson>
<representedOrganization>
<id extension="1120456789" root="1.2.250.1.71.4.2.2"></id>
<name>Organisation-Y</name>
<telecom nullFlavor="UNK"></telecom>
<addr nullFlavor="UNK"></addr>
</representedOrganization>
</assignedAuthor>
</author>
```
#### Instruction

1. Décoder le document CDA
Pour cela il faut récuperer le document CDA qui est dans le champ **OBX-5.4** 
2. Générer un nouvelle identifiant de document
4. Remplacer l'identifiant de la structure de l'auteur du document CDA
5. Re-encoder en base 64 le document CDA



#### Instruction

Dans ce cas, il vous faudra modifier l'identifiant du document remplacé dans le document CDA et la valeur du champ **TXA-13**

### Synthèse des modifications à effectuer dans le message HL7v2

| Segment  | Champs          | Description | Instruction |
| :--------------- |:---------------| :-----:| :-----|
| MSH  |   MSH-3        |  Application émettrice  | |
| MSH  | MSH-4          |   Organisation émettrice  |  |
| MSH  | MSH-5          |    Application réceptrice  | |
| MSH  | MSH-6          |   Organisation réceptrice | |
| MSH  | MSH-7          |    Date/time du message | |
| MSH  | MSH-10          |   Identifiant du message  | |
| OBX  | OBX-5.4         |  Document CDA encodé en base 64    | modifié Id du document principal et/ou du document remplacé et le champ author/assignedAuthor/representedOrganization/id |






