# Messages PAM-Fr dans le cadre du SGL
Vous trouverez sur cette page les templates de message PAM dans le cadre du référentiel SGL 


## Liste des templates

Pour l'ensmeble des message, le patient utilisé est le patient "PAT-TROIS DOMINIQUE". Il ne faut pas modifier cet élement.

Par contre d'autres segments sont à modifier en fonction de votre configuration, vous trouverez ci-dessous la liste :  

| Segment  | Champs          | Description | Instruction |
| :--------------- |:---------------| :-----:| :-----|
| MSH  |   MSH-3        |  Application émettrice  | |
| MSH  | MSH-4          |   Organisation émettrice  |  |
| MSH  | MSH-5          |    Application réceptrice  | |
| MSH  | MSH-6          |   Organisation réceptrice | |
| MSH  | MSH-7          |    Date/time du message | |
| MSH  | MSH-10          |   Identifiant du message  | |
| OBX  | OBX-5.4         |  Document CDA encodé en base 64    | 


### Template Admission (ADT^01)
Le template [admission.er7](admission.er7) est à utilisé pour l'exigence "SC.DMP/ALI/PROG.10 : 
- Consentement d'alimentation au DMP
- Modfification de l'UF
- Modification du séjour
 
# Template sortie (ADT^03)
Le template [sortie.er7](sortie.er7) est à utilisé pour l'exigence  SC.DMP/ALI/PROG.11 : 
- Consentement d'alimentation au DMP
- Modfification de l'UF
- Modification du séjour
