# Exemples de messages ORU en HL7 v2.5

## Description

Vous trouverez sur cette page des exemples de messages ORU en HL7 v2.5 dans le contexte du volet "Transmission de document(s) CDA en HL7v2".

**NB : Ces exemples sont hors périmètre du SEGUR.**

## Contenu

- le répertoire **Transmission initiale ORU**
  - contient un exemple de message HL7v2 ORU qui contient un CR de biologie au format CDA N1 et le même contenu clinique au format CDA N3. Il s'agit de deux documents différents au même contenu clinique mais au format différent transmis par le Créateur au Gestionnaire pour la première fois. Cette possibilité n'est pas applicable au SEGUR vague 2, elle a été maintenue pour des systèmes qui ne seraient pas référencés SEGUR vague 2 et qui souhaiteraient continuer à utiliser ce mécanisme. Pour les systèmes référencés vague 2, le CDA structuré de niveau 3 intègre le PDF correspondant dans une section dédiée du CDA Niv3. Un exemple est fourni ici avec le CR CR_BIO_2023.01_Electrophorese.xml.
- le répertoire **Remplacement ORU** : 
  - contient un exemple de message HL7v2 ORU qui contient une nouvelle version des 2 documents CDA N1 et CDA N3 précédemment transmis. le champ OBX-11 des segments OBX portant les nouvelles versions de document prend la valeur C indiquant ainsi une demande de remplacement des documents initiaux. le lien avec la version précédente du document est indiqué par l'élément relatedDocument au niveau du CDA.
- le répertoire **Suppression ORU** : 
  -contient un exemple de message HL7v2 ORU qui contient la dernière version des documents à supprimer. le champ OBX-11 des segments OBX portant les documents prend la valeur D pour indiquer une demande de suppression
