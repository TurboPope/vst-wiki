# UMLSec

> ich kanns dir auch einfach grad schnell erklären

> deine verbindungen zwischen den komponenten sind ja mit stereotypen markiert

> also sowas wie `<<LAN>>` `<<Internet>>`

> er hat dann ne funktion gemacht die Threat_A(x) funktion, die übernimmt als x einen solchen stereotyp und gibt aus welche angriffe möglich sind wenn es sich um einen angreifer A handelt

> secure link ermöglicht es dir verbindungen zwischen artefakten mit `<<integrity>>` `<<secrecy>>` oder `<<high>>` zu markieren

> und es gibt da eigentlich nur 3 bedingungen

> wenn eine verbindung mit `<<secrecy>>` markiert ist, dann darf kein angriff mit read möglich sein, also darf threat_A(x) nicht "read" enthalten

> wenn eine verbindung mit `<<inetgrity>>` markiert ist, dann darf kein angriff mit insert möglich sein, also darf threat_A(x) nicht "insert" enthalten

> wenn eine verbindung mit `<<high>>` markiert ist, dann darf kein angriff möglich sein, also darf threat_A(x) nicht nichts enthalten

> das ist alles... hauptsache der macht das mega dumm und umständich
