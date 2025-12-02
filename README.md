# PlanifiumHelper – Phase 2

Projet du cours **IFT2255 – Génie logiciel** (DIRO, UdeM).

L’objectif du système est d’aider les étudiants à faire des choix de cours éclairés en
s’appuyant sur les données officielles de l’API **Planifium** (cours, prérequis, horaires).
Cette phase se concentre sur le backend (API REST) et couvre :

- la **recherche de cours** ;
- l’**affichage des détails d’un cours** ;
- la **comparaison de plusieurs cours**.

---

## 1. Prérequis

- Java **JDK 19**
- Maven 3.x
- IntelliJ IDEA (recommandé)

---

## 2. Lancer l’application

### Depuis IntelliJ

1. Ouvrir le projet Maven (`pom.xml`).
2. Ouvrir `src/main/java/com/diro/ift2255/Main.java`.
3. Clic droit → **Run 'Main.main()'**.
4. Le serveur démarre sur : `http://localhost:7000`.

---

## 3. Endpoints

Base URL : `http://localhost:7000`

- `GET /ping`  
  → Test simple, retourne `"pong"`.

- `GET /courses-fake`  
  → Liste de cours codée en dur (pour test).

- `GET /courses?sigles=IFT2255,IFT2015`  
  → Recherche par sigles. Utilise l’API Planifium `/api/v1/courses?courses_sigle=...&response_level=min`.

- `GET /courses?name=logiciel`  
  → Recherche par mot-clé dans le nom du cours.

- `GET /courses/IFT2255`  
  → Détails complets du cours IFT2255 (description, prérequis, disponibilités, etc.).

- `GET /compare?sigles=IFT2255,IFT2015`  
  → Comparaison de plusieurs cours. Retourne une liste de `CourseDetails`.

Ces endpoints couvrent les cas d’utilisation de la phase 2 :
**recherche de cours**, **voir les détails**, **comparer des cours**.

---

## 4. Lancer les tests

```bash
mvn test
