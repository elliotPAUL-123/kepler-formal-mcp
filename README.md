# kepler-formal-mcp

## Utilisation

Pour utiliser ce MCP, il suffit de:

1. Cloner le dépôt avec les sous-modules, ou initialiser le sous-module après coup.
2. Lancer le script de build:

```bash
./build_kepler_formal.sh
```

Si tu veux aussi installer automatiquement les dépendances système, lance:

```bash
./build_kepler_formal.sh --install-deps
```

Ce script va récupérer `kepler-formal`, initialiser ses sous-modules, puis compiler le binaire dans `thirdparty/kepler-formal/build/`.

Le dépôt contient maintenant `kepler-formal` comme vrai sous-module Git dans `thirdparty/kepler-formal`.

Ensuite, `server.py` cherche automatiquement le binaire généré dans le bon dossier, donc il n’y a pas d’étape manuelle supplémentaire pour le retrouver.

## Dépendances

Sur Linux Ubuntu/Debian:

```bash
sudo apt-get install g++ libboost-dev python3.9-dev capnproto libcapnp-dev libtbb-dev pkg-config bison flex doxygen libspdlog-dev libfmt-dev libboost-iostreams-dev zlib1g-dev
```

Sur Fedora:

```bash
sudo dnf install gcc-c++ boost-devel python3-devel capnproto capnproto-devel tbb-devel pkgconf-pkg-config bison flex doxygen spdlog-devel fmt-devel boost-iostreams-devel zlib-devel cmake git
```

Sur macOS avec Homebrew:

```bash
brew install cmake doxygen capnp tbb bison flex boost spdlog zlib
```

Sous Windows, le plus simple est de passer par WSL2 ou MSYS2 avec un environnement Bash compatible. L’installation automatique des dépendances système n’est pas prévue pour Windows natif.