# Messages PAM-Fr dans le cadre du SGL
Vous trouverez sur cette page les templates de message PAM dans le cadre du référentiel SGL.

Ces templates sont à utiliser tels quels en adaptant uniquement les éléments listés ci-dessous. **Ne pas modifier le segment PID. Pour le template d’admission uniquement, ne pas modifier le segment ZFA, qui porte les valeurs de référence liées au statut DMP / consentement. Le template de sortie ne comporte pas de segment ZFA** — ils contiennent le patient de test "PAT-TROIS DOMINIQUE" et des valeurs de référence.

## Éléments à modifier

| Segment | Champ | Description |
| :------- | :----- | :---------- |
| MSH | MSH-3 | Application émettrice |
| MSH | MSH-4 | Organisation émettrice |
| MSH | MSH-5 | Application réceptrice |
| MSH | MSH-6 | Organisation réceptrice |
| MSH | MSH-7 | Date/heure du message |
| MSH | MSH-10 | Identifiant du message |
| EVN | EVN-2 | Date/heure d'enregistrement de l'événement |
| EVN | EVN-6 | Date/heure de survenue de l'événement |
| PV1 | PV1-3 | UF d'hébergement (localisation du patient) |
| ZBE | ZBE-1 | Identifiant du mouvement |
| ZBE | ZBE-2 | Date/heure de création du mouvement |
| ZBE | ZBE-7 | UF de responsabilité médicale |
| ZBE | ZBE-8 | UF de responsabilité des soins |

## Éléments à ne pas modifier

| Segment | Description |
| :------- | :---------- |
| PID | Identification du patient — contient le patient de test "PAT-TROIS DOMINIQUE" |
| ZFA | Statut DMP / consentement — valeurs de référence à ne pas modifier (admission uniquement) |


## Templates

### Template Admission (ADT^A01)

Le template [admission.er7](admission.er7) est à utiliser pour l'exigence SC.DMP/ALI/PROG.10 :
- Consentement d'alimentation au DMP

#### Segments du message admission.er7

| Segment | Description | Champs |
| :------- | :---------- | :----- |
| MSH | Message Header – en-tête du message | MSH-3 Application émettrice, MSH-4 Organisation émettrice, MSH-5 Application réceptrice, MSH-6 Organisation réceptrice, MSH-7 Date/heure, MSH-10 Identifiant du message |
| EVN | Event Type – type d'événement déclencheur | EVN-2 Date/heure d'enregistrement, EVN-6 Date/heure de survenue |
| **PID** | **Patient Identification — ne pas modifier** | Contient le patient de test "PAT-TROIS DOMINIQUE" |
| PV1 | Patient Visit – informations de la venue | PV1-2 Classe de patient, PV1-3 **UF d'hébergement à modifier**, PV1-19 Numéro de venue, PV1-51 Visit Indicator |
| ZBE | Mouvement du patient (extension IHE France) | ZBE-1 Identifiant du mouvement, ZBE-2 Date/heure du mouvement, ZBE-4 Code action, ZBE-5 Indicateur historique, ZBE-7 **UF responsabilité médicale à modifier**, ZBE-8 **UF responsabilité des soins à modifier**, ZBE-9 Nature du mouvement |
| **ZFA** | **Statut DMP / consentement — ne pas modifier** | ZFA-1 Statut DMP, ZFA-2 Date de recueil |


### Template Sortie (ADT^A03)

Le template [sortie.er7](sortie.er7) est à utiliser pour l'exigence SC.DMP/ALI/PROG.11 :
- Fin de prise en charge

#### Segments du message sortie.er7

| Segment | Description | Champs |
| :------- | :---------- | :----- |
| MSH | Message Header – en-tête du message | MSH-3 Application émettrice, MSH-4 Organisation émettrice, MSH-5 Application réceptrice, MSH-6 Organisation réceptrice, MSH-7 Date/heure, MSH-10 Identifiant du message |
| EVN | Event Type – type d'événement déclencheur | EVN-2 Date/heure d'enregistrement, EVN-6 Date/heure de survenue |
| **PID** | **Patient Identification — ne pas modifier** | Contient le patient de test "PAT-TROIS DOMINIQUE" |
| PV1 | Patient Visit – informations de la venue | PV1-2 Classe de patient, PV1-3 **UF d'hébergement à modifier**, PV1-19 Numéro de venue, PV1-51 Visit Indicator |
| ZBE | Mouvement du patient (extension IHE France) | ZBE-1 Identifiant du mouvement, ZBE-2 Date/heure du mouvement, ZBE-4 Code action, ZBE-5 Indicateur historique, ZBE-7 **UF responsabilité médicale à modifier**, ZBE-8 UF responsabilité des soins, ZBE-9 Nature du mouvement |
