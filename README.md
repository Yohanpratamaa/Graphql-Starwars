# Langkah-Langkah Untuk bisa menjalankan Update dan Delete User dan Kapal

Kita akan menjalankan proyek wkwkwkwkwk.

## 1. Masuk ke folder proyek:

```bash
cd starwars-graphql-api
cd venv
```

## 2. Menjalankan proyek:

```bash
uvicorn main:app --reload
```

## 3. Mengunjungi Website Graphqlnya
Buka http://127.0.0.1:8000/graphql untuk mengakses GraphiQL, antarmuka interaktif untuk menguji API.

## 4. Untuk Mengujinya
### Update User/Karakter
```graphql
mutation {
  updateCharacter(input: {
    id: "1",
    name: "Luke Skywalker",
    species: "Human",
    homePlanetId: "1"
  }) {
    id
    name
    species
    homePlanet {
      name
    }
  }
}
```

### Delete User/Karakter
```graphql
mutation {
  deleteCharacter(id: "1")
}
```

### Create Kapal Baru
```graphql
mutation {
  createStarship(input: {
    name: "Death Star",
    model: "DS-1 Orbital Battle Station",
    manufacturer: "Imperial Department of Military Research"
  }) {
    id
    name
    model
    manufacturer
  }
}

```
### Update Kapal
```graphql
mutation {
  updateStarship(input: {
    id: "1",
    name: "Millennium Falcon",
    model: "YT-1300f light freighter",
    manufacturer: "Corellian Engineering Corporation"
  }) {
    id
    name
    model
    manufacturer
  }
}
```
### Hapus Kapal
```graphql
mutation {
  deleteStarship(id: "1")
}
```
### Hapus Kapal dari Karakter
```graphql
mutation {
  removeStarshipFromCharacter(input: {
    characterId: "1",
    starshipId: "1"
  }) {
    id
    name
    pilotedStarships {
      name
    }
  }
}
```

### Update Planet Asal Karakter
```graphql
mutation {
  updateCharacterHomePlanet(input: {
    characterId: "1",
    planetId: "2"
  }) {
    id
    name
    homePlanet {
      name
    }
  }
}
```
