# Entitats i Atributs

## Recinte
Un recinte té un nom que l'identifica, els metres quadrats d'escenari, els metres quadrats per als espectadors, aforament, si té lavabos i si el escenari es covert.    
    Recinte (Nom (PK), MetresQuadratsEscenari, MetresQuadratsEspectadors, Aforament,Lavabos ,EscenariCobert)

## Grup
Un grup té un nom que l'identifica, el pais d'origen, el preu, a qui substitueix en cas de que sigui un grup substitutata, i si es la principal en nom del substitut.    
    Grup(Nom (PK), País, NombreComponents, Preu, NomPrincipal, NomSubstitut)
        on NomPrincipal Referència Grup(NomGrup)
        on NomSubstitut Referència Grup(Nom)

## Concert
Un concert te una data dque l'identifica, el nom de la grup que toca, el recinte i l'hora d'inici.   
    Concert(Data (PK), NomGrup (FK), IdRecinte (FK), HoraInici)
        on NomGrup Referència Grup(Nom)
        on NomRecinte Referència Recinte(Nom)

## Carrer
Un carrer te un identificador propi i el nom.   
    Carrer(IdCarrer (PK), NomGrup)

## Parcel·la
Una parcel·la te un identificador propi, tambe el codi del carrer al que pertany, els metres quadrats, preu i la disponibilitat.  
    Parcel·la(IdParcel·la (PK), IdCarrer (FK), MetresQuadrats, Preu, Disponible)
        on IdCarrer Referència Carrer(IdCarrer)


## Usuari
    Persona(IdUsuari (PK), Usuari, Contrasenya, DniPassaport, Email, Nom, Cognoms, DataNaixement)

## Lloguer
    Lloguer(IdLloguer (PK), IdParcel·la (FK), UsuariResponsable (FK))
        on IdParcel·la Referència Parcel·la(IdParcel·la)
        on UsuariResponsable Referència Ususari(IdUsuari)


## Accés
    Accés(IdAcces (PK), IdUsuari (FK), IdRecinte (FK), DataEntrada, HoraEntrada, DataSortida, HoraSortida)
        on IdUsuari Referència Ususari(IdUsuari)
        on IdRecinte Referència Recinte(IdRecinte)

# Model Relacional