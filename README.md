# Entitats i Atributs

## Recinte
    Recinte (IdRecinte (PK), Nom, MetresQuadratsEscenari, MetresQuadratsEspectadors, Aforament,Lavabos ,EscenariCobert)

## Grup
    Grup(IdGrup (PK), Nom, País, NombreComponents,Preu)

## Substitut
    Substitut(IdPrincipal (FK), IdSubstitut (FK))
        on IdPrincipal Referència Grup(IdGrup)
        on IdSubstitut Referència Grup(IdGrup)


## Concert
    Concert(IdConcert (PK), IdGrup (FK), IdRecinte (FK), Data, HoraInici, HoraFi, Preu)
        on IdGrup Referència Grup(IdGrup)
        on IdRecinte Referència Recinte(IdRecinte)

## Carrer
    Carrer(IdCarrer (PK), NomGrup)

## Parcel·la
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