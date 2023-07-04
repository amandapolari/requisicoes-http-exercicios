# HTTPS e Postman - Resolução

## Índice

-   [1. Resolução Exercício 1](#1-resolução-exercício-1)
-   [2. Resolução Exercício 2](#2-resolução-exercício-2)
-   [3. Resolução Exercício 3](#3-resolução-exercício-3)

### 1. Resolução Exercício 1

[✔] Realizei a leitura desse material: [API Labefy](https://documenter.getpostman.com/view/7549981/SztBc8eT?version=latest)

[✔] Abrir a API no Postman com os seguintes passos:

1. ![Alt text](image.png)
2. ![Alt text](image-1.png)
3. ![Alt text](image-2.png)

* Traduzi os métodos para facilitar a manipulação:
![Alt text](image-3.png)

---

### 2. Resolução Exercício 2

**[✔] a) Crie três playlists:**

-   `createPlaylist` -> `Headers` :

    ```
    Authorization: "nome-sobrenome-turma"
    ```

-   `createPlaylist` -> `Body` :

    ```
    {
        "name": "string"
    }
    ```

    Obs: `name` -> é o nome da playlist que desejo criar.

*   Resultado:

    ```
    Status: 200 OK
    ```

* Para criar mais duas playlist, repeti os passos anteriores mais duas vezes.

**[✔] b) Verifique se elas foram criadas corretamente.**

-   `getAllPlaylists` -> `Headers` :

    ```
    Authorization: "nome-sobrenome-turma"
    ```

*   `Resultado:`

    ```
    Status: 200 OK
    ```


    ```
    {
        "result": {
            "quantity": 3,
            "list": [
                {
                    "id": "61ca160b-25d0-4fad-a8f7-274055419cf5",
                    "name": "playlist animada"
                },
                {
                    "id": "35471f8a-2997-48eb-b1bc-746d384ed923",
                    "name": "playlist estudos"
                },
                {
                    "id": "0c92f366-4648-4659-89fe-b0367ae81740",
                    "name": "playlist relaxar"
                }
            ]
        }
    }
    ```

**[✔] c) Adicione duas músicas em cada uma delas.**

-   `addTrackToPlaylist` -> `Headers` :
    ```
    Authorization: "nome-sobrenome-turma"
    ```
-   `addTrackToPlaylist` -> `Params` -> `Path Variables` :

    ```
    playlistId: id da playlist
    ```

-   `addTrackToPlaylist` -> `Body` :

    ```
    {
        "name": "string",
        "artist": "string",
        "url": "string"
    }
    ```

    -   Obs:
        -   name -> nome da música;
        -   artist -> cantor ou banda da música;
        -   url -> URL da música para ser tocada;

-   Repeti os processo para cada música que desejei adicionar a cada playlist.

**[✔] d) Verifique se as músicas foram adicionadas corretamente.**

-   `getPlaylistTracks` -> `Headers` :

    ```
    Authorization: "nome-sobrenome-turma"
    ```

-   `getPlaylistTracks` -> `Params`:

    ```
    playlistId: id da playlist
    ```

*   `Resultado:`

-   ```
    {
        "result": {
            "quantity": 3,
            "tracks": [
                {
                    "id": "d0fd86b4-b80e-4464-bbe0-94d09fb5f7b0",
                    "name": "Happy",
                    "artist": "Pharrell Williams",
                    "url": "https://www.youtube.com/watch?v=ZbZSe6N_BXs&ab_channel=PharrellWilliamsVEVO"
                },
                {
                    "id": "c2072c28-278e-46bf-8466-c4a945983536",
                    "name": "Don't Start Now ",
                    "artist": "Dua Lipa",
                    "url": "https://www.youtube.com/watch?v=oygrmJFKYZY&list=PLa26d-dWyowFl4J9datdy3pxTk0ZXq-At&index=34&ab_channel=DuaLipa"
                },
                {
                    "id": "fe2c0bb3-2009-42f3-bea3-2f4af332ab83",
                    "name": "So What",
                    "artist": "Pink",
                    "url": "https://www.youtube.com/watch?v=FJfFZqTlWrQ&list=PLa26d-dWyowFl4J9datdy3pxTk0ZXq-At&index=42&ab_channel=PinkVEVO"
                }
            ]
        }
    }
    ```

    ```
    Status: 200 OK
    ```

### 3. Resolução Exercício 3

**[✔] a) Pesquise por uma das playlists que você criou.**

-   `searchPlaylist` -> `Headers`:

    ```
    Authorization: "nome-sobrenome-turma"
    ```

-   `searchPlaylist` -> `Params`:

    ```
    name:"string"
    ```

    Obs: name -> nome da playlist ou parte dele

-   `Resultado:`

    ```
    {
    "result":
    {
        "quantity": 1,
        "playlist": [
            {
                "id": "0c92f366-4648-4659-89fe-b0367ae81740",
                "name": "playlist relaxar"
            }
        ]
    }
    }
    ```

    ```
    Status: 200 OK
    ```

**[✔] b) Remova uma música de uma playlist.**

-   `removeTrackFromPlaylist` -> `Headers`

    ```
    Authorization: "nome-sobrenome-turma"
    ```

-   `removeTrackFromPlaylist` -> `Params`:

    ```
    playlistId: id da playlist
    trackId: id da música
    ```

-   `Resultado:`

    ```
    Status: 200 OK
    ```

**[✔] c) Delete outra playlist.**

-   `deletePlaylist` -> `Headers`

    ```
    Authorization: "nome-sobrenome-turma"
    ```

-   `deletePlaylist` -> `Params`:

    ```
    playlistId: id da playlist
    ```

-   `Resultado:`
    ```
    Status: 200 OK
    ```
