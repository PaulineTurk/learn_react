# Bundle
- gros fichier js optimisé
- fusion de fichiers js

# Bundler
- outil de création de bundle ex. vite est un bundler

# HMR = Hot Module Replacement
- le navigateur recharge uniquement les composants dont le state a changé
- évite de recharger toute la page à chaque modification de composant
- évite de perdre l'état d'avancement de la page en cours

# JSX = JavaScript XML
- extension de js pour autoriser du HTML dans du js
- adaptation du code HTML dans du jsx
    1. un seul élément racine
    2. **className** au lieu de **class** car class est un terme consacré en ts
    3. **htmlFor** au lieu de **for**
    4. **{}** dans le HTML pour injecter du js
    5. auto-closing obligatoire pour toutes les balises, même si en HTML c'est inutile ex. <img/> pas <img>
- tsx c'est pareil que jsx mais en TypeScript
- Pour JSX, <ThisComponent /> est un composant React, mais <thiscomponent> est un tag HTML

# Node.js
- environnement d'exécution (runtime) de JavaScript qui fonctionne en dehors d'un navigateur
- donne accès au système (fs = file system): fichiers, processus, ...
- crée des serveurs (http)
- programmé codé en javascript et C++ 
- n'est pas un navigatuer, ni une émulation de navigateur
- même moteur que navigatuer, V8 engine, mais APIs complètement différente
  - navigatuer: DOM, window, web APIs
  - Node.js: module core, libuv(I/O), bindings C++

# Puppeteer
- navigateur headless

# Navigateur
- DOM
- objet window
- rendering engine (moteur de rendu)
- web API ex. localStorage

# Anti-pattern React sur le hook useState
## ou Principe d'immutabilité en React
- React fait une optimisation en ne regardant pas le contenu des objets mais seulement leur référence. Ainsi, l'anti-pattern en React est de modifier les valeurs dans un objet **du state**. Ceci ne provoquera pas de re-render. C'est pourquoi, il faut toujours prendre une copie d'un objet **du state** avant de le modifier et le passer à **setState**.
- Dans les states React, on ne mute pas des objets, on les recrée.

# React re-render asynchrone
- La nouvelle valeur d'un render n'est JAMAIS accessible via la variable dans le même render. La nouvelle valeur n'est accessible qu'au prochain render
- Ainsi setState1 puis setState2 est équivalent à setState2 puis setState1