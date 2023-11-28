Vous trouverez sur cette page un exemple de message HL7v2.6 MDM correspondant à une demande de remplacement du CR d'imagerie médicale provenant d'un courriel réceptionné par le FOURNISSEUR de documents (la PFI). 
le message MDM contient la nouvelle version du CR (version 2) sur lequel le nom du patient a été modifié (PatA vers PatientA) ainsi que les niveaux de confidentialité : le CR est passé de l'état invisible à l'état visible au patient et à ses représentants légaux. En conséquence, la métadonnée MODIF_CONF_CODE prend la valeur "Y" pour indiquer une modification des niveaux de confidentialité.

le remplacement/mise à jour des métadonnées du CR est transmise au DPI de l'hôpitaA. Au niveau du message MDM, la demande de remplacement/maj métadonnées est indiquée par la valeur de l'OBX-11 ("C")

Remplacement du CR d'imagerie:

- le document CR_Radio_CDAN1_v2.XML au format CDA N1 (nouvelle version),
- le message message_MDM__LPS_MSS_CR_Radio_RPLC_N1.er7 qui permet de transmettre la demande de remplacement du CR vers le CONSOMMATEUR (DPI ou RIS),
- l'acquittement technique du message HL7.
