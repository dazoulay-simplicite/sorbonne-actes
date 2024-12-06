<!--
 ___ _            _ _    _ _    __
/ __(_)_ __  _ __| (_)__(_) |_ /_/
\__ \ | '  \| '_ \ | / _| |  _/ -_)
|___/_|_|_|_| .__/_|_\__|_|\__\___|
            |_| 
-->
![](https://platform.simplicite.io/logos/standard/logo250.png)
* * *

`SorbonneActes` module definition
=================================



`SrbaActe` business object definition
-------------------------------------



### Fields

| Name                                                         | Type                                     | Required | Updatable | Personal | Description                                                                      |
|--------------------------------------------------------------|------------------------------------------|----------|-----------|----------|----------------------------------------------------------------------------------|
| `srbaActIdentifiant`                                         | char(50)                                 | yes*     | yes       |          | -                                                                                |
| `srbaActLibelle`                                             | char(255)                                | yes      | yes       |          | -                                                                                |
| `srbaActDate`                                                | date                                     |          | yes       |          | -                                                                                |
| `srbaActDescription`                                         | html(100)                                |          | yes       |          | -                                                                                |
| `srbaActDocuments`                                           | document                                 |          | yes       |          | -                                                                                |

`SrbaInstitution` business object definition
--------------------------------------------



### Fields

| Name                                                         | Type                                     | Required | Updatable | Personal | Description                                                                      |
|--------------------------------------------------------------|------------------------------------------|----------|-----------|----------|----------------------------------------------------------------------------------|
| `srbaInsNom`                                                 | char(255)                                | yes*     | yes       |          | -                                                                                |
| `srbaInsDescription`                                         | html(1000000)                            |          | yes       |          | -                                                                                |

`SrbaPrsAct` business object definition
---------------------------------------



### Fields

| Name                                                         | Type                                     | Required | Updatable | Personal | Description                                                                      |
|--------------------------------------------------------------|------------------------------------------|----------|-----------|----------|----------------------------------------------------------------------------------|
| `srbaPrsactPrsId` link to **`SrbPersonne`**                  | id                                       | yes*     | yes       |          | -                                                                                |
| _Ref. `srbaPrsactPrsId.srbaPrsNom`_                          | _char(100)_                              |          |           |          | -                                                                                |
| _Ref. `srbaPrsactPrsId.srbaPrsPrenoms`_                      | _char(100)_                              |          |           |          | -                                                                                |
| _Ref. `srbaPrsactPrsId.srbaPrsInsId`_                        | _id_                                     |          |           |          | -                                                                                |
| _Ref. `srbaPrsInsId.srbaInsNom`_                             | _char(255)_                              |          |           |          | -                                                                                |
| `srbaPrsactActId` link to **`SrbaActe`**                     | id                                       | yes*     | yes       |          | -                                                                                |
| _Ref. `srbaPrsactActId.srbaActIdentifiant`_                  | _char(50)_                               |          |           |          | -                                                                                |
| `srbaPrsactRole`                                             | enum(100) using `SRBA_PRSACT_ROLE` list  |          | yes       |          | -                                                                                |

### Lists

* `SRBA_PRSACT_ROLE`
    - `AUTEUR` Auteur
    - `TEMOIN` Témoin
    - `DESTINATAIRE` Destinataire
    - `METIONNE` Mentionné

`SrbPersonne` business object definition
----------------------------------------



### Fields

| Name                                                         | Type                                     | Required | Updatable | Personal | Description                                                                      |
|--------------------------------------------------------------|------------------------------------------|----------|-----------|----------|----------------------------------------------------------------------------------|
| `srbaPrsNom`                                                 | char(100)                                | *        | yes       |          | -                                                                                |
| `srbaPrsPrenoms`                                             | char(100)                                |          | yes       |          | -                                                                                |
| `srbaPrsInsId` link to **`SrbaInstitution`**                 | id                                       |          | yes       |          | -                                                                                |
| _Ref. `srbaPrsInsId.srbaInsNom`_                             | _char(255)_                              |          |           |          | -                                                                                |

