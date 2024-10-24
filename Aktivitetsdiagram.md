::: mermaid

flowchart TD
Start((Start))
Slutt((Slutt))
VelgFilm(Velg film)
VelgTidspunkt(Velg tidspunkt og dato)
VelgSete(Velg sete)
VelgTypeBillett(Velg type billett - vr eller vanlig)
BekreftBestilling(Bekreft bestilling)
AntallBilletter(Velg antall billetter)
Betal(Fyll inn betalingsinnformasjon)
Kvittering(Ny billett)

RiktigFilm{Har du valgt riktig film?}
RiktigTidspunkt{Riktig tidspunkt?}
RiktigSete{Ønsker du dette sete?}
RiktigBillett{Ønsker du denne billetttypen?}
RiktigOrdre{Bekreft at orderen din er riktig}
BetalingGodkjent{Godkjent?}

Start --> VelgFilm
VelgFilm --> RiktigFilm
RiktigFilm --> |JA|VelgTidspunkt
RiktigFilm --> |NEI|VelgFilm
VelgTidspunkt --> RiktigTidspunkt
RiktigTidspunkt --> |JA|VelgSete
RiktigTidspunkt --> |NEI|VelgTidspunkt
VelgSete --> RiktigSete
RiktigSete --> |JA|VelgTypeBillett
RiktigSete --> |NEI|VelgSete
VelgTypeBillett --> AntallBilletter
AntallBilletter --> RiktigBillett
RiktigBillett --> |JA|BekreftBestilling
RiktigBillett --> |NEI|VelgTypeBillett
BekreftBestilling --> RiktigOrdre
RiktigOrdre --> |JA|Betal
RiktigOrdre --> |NEI|Start
Betal --> BetalingGodkjent
BetalingGodkjent --> |JA|Kvittering
BetalingGodkjent --> |NEI|Betal
Kvittering --> Slutt

:::