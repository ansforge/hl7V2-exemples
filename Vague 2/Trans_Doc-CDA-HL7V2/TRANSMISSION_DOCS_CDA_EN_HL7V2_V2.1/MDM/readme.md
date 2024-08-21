Vous trouverez sur cette page des exemples de messages MDM en HL7v2.6 dans le contexte du volet "Transmission de document(s) CDA en HL7v2, vague2".
- le répertoire **Transmission initiale MDM** :
  - contient un exemple de message HL7v2 MDM qui contient un CR d'imagerie médicale au format CDA N1 transmis au GESTIONNAIRE pour la première fois.
- le répertoire **Remplacement MDM** :
  - contient un exemple de message HL7v2 MDM qui contient une nouvelle version du document CDA N1 précédemment transmis. le champ OBX-11 du segment OBX portant la nouvelle version de document prend la valeur C indiquant ainsi une demande de remplacement du document initial. le lien avec la version précédente du document est indiqué par l'élément relatedDocument au niveau du CDA.
- le répertoire **Suppression MDM**  :
  - contient un exemple de message HL7v2 MDM qui contient la dernière version d'un document à supprimer. le champ OBX-11 du segment OBX portant le document prend la valeur D pour indiquer une demande de suppression.



