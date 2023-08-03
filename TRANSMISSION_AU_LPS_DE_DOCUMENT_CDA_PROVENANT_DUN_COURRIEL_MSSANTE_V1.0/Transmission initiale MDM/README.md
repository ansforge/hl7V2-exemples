Vous trouverez sur cette page un exemple de message HL7v2.6 MDM correspondant à une transmission initiale d'un CR d'imagerie médicale issu d'un courriel reçu par la PFI.
Ce CR concerne le patient Domininique PatA. l'expéditeur est le Dr Thomas Eric. Le CR est transmis au DPI de l'hôpitalA via le message MDM. Le Cr est masqué au patient et à ses représentants légaux. L'expéditeur n'a pas demandé à reçevoir un accusé de lecture des informations portées par le message MDM. 

Transmission initiale MDM:
- le document CR_Radio_CDAN1_v1.XML au format CDA N1,inclu dans le message,
    - le message HL7 MDM message_MDM__LPS_MSS_CR_Radio_INIT_N1.er7 qui permet de transmettre le document du GESTIONNAIRE vers le CONSOMMATEUR,
    - le message HL7 MDM message_MDM__LPS_MSS_CR_Radio_INIT_N1_Base64.er7, identique au précédent mais contenant le document en Base64,
    - l'acquittement technique du message HL7.

