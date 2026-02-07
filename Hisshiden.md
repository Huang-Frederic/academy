# Hisshiden - Journal des Modifications Serveur

> Cobblemon Academy Legacy - Serveur optimise pour ~10 joueurs

---

## 1. Taux de Shiny

### Taux de base
| Parametre | Avant | Apres |
|-----------|-------|-------|
| `shinyRate` | 1/3072 | **1/2048** |

**Fichier** : `config/cobblemon/main.json`

### Shiny Charm (Charme Chroma)
| Parametre | Avant | Apres |
|-----------|-------|-------|
| Multiplicateur | x1.1 | **x1.5** |

Avec le Shiny Charm, le taux effectif passe a environ **1/1365**.

**Fichier** : `config/MoreSparkles/items.json`

### Autres boosters de shiny (inchanges)
- **Cobbreeding (Masuda)** : x4.0 en reproduction
- **KO Streak (Unchained)** : boost progressif selon les KO enchaines (jusqu'a x3 a 500 KO)
- **Lunes bleues** : x10 (Blue Moon), x16 (Super Blue Moon)

---

## 2. Structures du Monde

### Modificateur global d'espacement
| Parametre | Avant | Apres |
|-----------|-------|-------|
| `global_spacing_and_separation_modifier` | 2.0 (tres espace) | **1.3** (equilibre) |

**Fichier** : `config/structurify.json`

### Structures reactivees

#### Alpha Dens (Cobblemon Alphas)
- `cobblemonalphas:alpha_den_underground` - Taniere souterraine d'Alphas
- `cobblemonalphas:plains_den` - Taniere de plaines

#### Mega Showdown
- `mega_showdown:archaeological_site` - Site archeologique (Mega Stones)
- `mega_showdown:mega_site` - Site Mega
- `mega_showdown:megaroid` - Meteorite Mega
- `mega_showdown:wishing_weald` - Foret des Voeux (Power Spot Dynamax)

#### Rad Gyms (18 types + interieur)
Tous les gymnases par type ont ete reactives :
`bug`, `dark`, `dragon`, `electric`, `fairy`, `fighting`, `fire`, `flying`, `ghost`, `grass`, `ground`, `ice`, `normal`, `poison`, `psychic`, `rock`, `steel`, `water`
+ `gym_interior_default`

#### Minecraft vanilla
| Structure | Avant | Apres |
|-----------|-------|-------|
| Mineshafts | 0.0 (desactive) | **0.4** |
| Buried Treasures | 0.0 (desactive) | **0.3** |
| Trial Chambers | desactive | **reactive** |

#### Eternal Starlight (nouvellement reactivees)
- `eternal_starlight:cursed_garden` - Jardin Maudit
- `eternal_starlight:golem_forge` - Forge de Golem
- `eternal_starlight:portal_ruins_cold` - Ruines de Portail (froid)
- `eternal_starlight:portal_ruins_common` - Ruines de Portail (commun)
- `eternal_starlight:portal_ruins_desert` - Ruines de Portail (desert)
- `eternal_starlight:portal_ruins_forest` - Ruines de Portail (foret)
- `eternal_starlight:portal_ruins_jungle` - Ruines de Portail (jungle)
- `eternal_starlight:stranghoul_den` - Taniere de Stranghoul

#### MNS (nouvellement reactivee)
- `mns:copper_tower` - Tour de Cuivre

#### MSS (nouvellement reactivees)
- `mss:arena` - Arene de combat
- `mss:calcite_house` - Maison de Calcite
- `mss:volcano` - Volcan

#### MVS (nouvellement reactivees)
- `mvs:carts/cart` - Chariot
- `mvs:carts/large_cart_1` - Grand Chariot 1
- `mvs:carts/large_cart_2` - Grand Chariot 2
- `mvs:carts/medium_bamboo_cart` - Chariot Bambou Moyen
- `mvs:cathedral` - Cathedrale
- `mvs:houses/large_warped_tower` - Grande Tour Tordue

#### Trek (nouvellement reactivees)
- `trek:overworld/rare/villager_castle` - Chateau Villageois (rare)
- `trek:overworld/very_rare/coves` - Criques (tres rare)

#### ATI (nouvellement reactivee)
- `ati_structures:gnome_hut` - Hutte de Gnome

### Structures restant desactivees
- `minecraft:stronghold_big` (redondant avec minecraft:strongholds)

---

## 3. Items Legendaires & Loot Tables

### Systeme de tiers par distance

Les coffres du monde utilisent un systeme de tiers base sur la distance au spawn. Plus tu t'eloignes, meilleur est le loot.

#### Taux de drop d'item legendaire par tier (MODIFIE - taux uniforme 1/50)

| Tier | Distance approx. | Chance legendaire |
|------|------------------|-------------------|
| **t0** | Spawn | Aucune |
| **t1** | ~1000 blocs | **1/50** |
| **t2** | ~2000 blocs | **1/50** |
| **t3** | ~3000 blocs | **1/50** |
| **t4** | ~4000 blocs | **1/50** |
| **t5** | ~5000 blocs | **1/50** |
| **t6** | ~6000 blocs | **1/50** |
| **t7** | ~7000 blocs | **1/50** |
| **t8** | ~8000 blocs | **1/50** |
| **t9** | ~9000+ blocs | **1/50** |

> **Changement majeur** : Le taux de drop legendaire est maintenant **constant a 1/50 par coffre** pour tous les tiers a partir du t1. Seul le t0 (spawn) ne contient pas de legendaire.

**Fichiers modifies** : `loot_table/basic/t1.json` a `t9.json`, `loot_table/basic_underground/t1.json` a `t9.json`

### Loot pools uniformes t1-t9 (NOUVEAU)

A partir du t1, tous les coffres normaux et underground partagent les memes pools de loot uniformes, en plus de leurs pools specifiques au tier (monnaie, bonbons, medecine, vitamines, etc.).

#### Coffres normaux (`basic/t1-t9`)

| Pool | Taux | Details |
|------|------|---------|
| Pokeballs basiques (t1) | **1/3** | Poke Ball, Premier, Verdant, Azure, etc. (rolls 1-2) |
| Super Balls (t2) | **1/5** | Great Ball, Heal, Nest, Net, Luxury, etc. |
| Hyper Balls (t3) | **1/10** | Ultra Ball, Dusk, Repeat, Timer, Quick, etc. |
| Master Balls (t4) | **1/50** | Safari, Sport, Dream, Beast, Park, Master Ball |
| Fossiles | **1/30** | Fossiles normaux (90%) + Shiny/HA/MaxIV fossiles (10%) |
| Cles de gym | **1/30** | Toutes les 18 cles de type |
| CT/TMs | **1/15** | Tous les TMs disponibles |
| Pokeblocks | **1/30** | Common(50%), Uncommon(25%), Rare(15%), Epic(5%), Legendary(5%) |
| Pokeblock Shiny | **1/1024** | Pokeblock shiny rare |
| Legendaires | **1/50** | Items legendaires (systeme par biome) |
| Mega Stone | **1/50** | Pierre Mega aleatoire |
| Tera Shard | **1/50** | Fragment Tera aleatoire |
| Z-Crystal Type | **1/50** | Cristal Z de type aleatoire |
| Silvally Memory | **1/50** | Memoire Silvally aleatoire |
| Rotom Form | **1/50** | Forme Rotom aleatoire |
| Arceus Plate | **1/50** | Plaque Arceus aleatoire |
| Booster Pack | **1/20** | Pack booster |

#### Coffres underground (`basic_underground/t1-t9`)

Memes pools que les coffres normaux, avec les differences suivantes :
- **Fossiles** : taux double a **1/15** (au lieu de 1/30)
- Les pools tier-specifiques underground sont preserves (pokeballs anciennes, tumblestones, gems, etc.)

#### Pools tier-specifiques preserves

Les pools suivants varient encore selon le tier et sont preserves tels quels :
- Monnaie (`numismaticoverhaul/tX`)
- Bonbons (`candy_tX`)
- Medecine, Vitamines, Mints, X-items
- Pierres d'evolution, Items d'evolution
- Held items, Roasted/Smoked/Golden Apricorns
- Hot Kettles, Biome Blends
- Pokeballs anciennes (underground seulement)

**Fichiers modifies** : `loot_table/basic/t1.json` a `t9.json`, `loot_table/basic_underground/t1.json` a `t9.json`

### Loot des Gyms (MODIFIE - taux uniforme 1/20 + TMs)

Les gymnases Rad Gyms ont maintenant un taux de drop legendaire uniforme :
| Tier Gym | Chance legendaire (avant) | Chance legendaire (apres) |
|----------|---------------------------|---------------------------|
| Tous les tiers (t0-t10) | Variable (1/101 a 1/5) | **1/20** |

> Chaque victoire contre un Gym Leader donne une chance de **1/20** d'obtenir un item legendaire, quel que soit le tier du gym.

**Nouveau** : Un pool de **TMs/CTs** a ete ajoute a tous les gyms (t0-t10) avec un taux de **1/15**.

**Fichiers modifies** : `loot_table/basic_gym/t0.json` a `t10.json`

### Systeme de distribution par biome/theme (NOUVEAU)

Les items legendaires sont maintenant organises en **15 categories thematiques** au lieu d'un pool unique. Quand un drop legendaire arrive, il provient d'une de ces categories aleatoirement :

**Categories thematiques creees** :
1. **Fire/Volcanic** - Groudon, Heatran, Moltres, Entei, Volcanion (6 items)
2. **Water/Ocean** - Kyogre, Lugia, Articuno, Suicune, Tapu Fini, Urshifu-Water, Mew (7 items)
3. **Ice/Snow** - Regice, Glastrier, Articuno, Arceus (4 items)
4. **Electric/Storm** - Regieleki, Zapdos, Thundurus, Tapu Koko, Zeraora (5 items)
5. **Dragon/Dimensional** - Dialga, Palkia, Giratina, Rayquaza, Kyurem, Zekrom, Reshiram (7 items)
6. **Forest/Nature** - Xerneas, Virizion, Cobalion, Keldeo, Wo-Chien, Tapu Bulu, Ogerpon, Celebi, Shaymin, Zarude, Genesect (12 items)
7. **Dark/Spectral** - Yveltal, Spectrier, Cresselia, Urshifu-Dark, Darkrai, Marshadow, Hoopa (7 items)
8. **Cosmic/Celestial** - Cosmog, Necrozma, Solgaleo, Lunala, Deoxys, Naganadel, Magearna (7 items)
9. **Steel/Tech** - Type: Null, Eternatus, Zacian, Zamazenta, Registeel, Miraidon, Koraidon, Genesect, Meltan/Melmetal (10 items)
10. **Rock/Underground** - Regirock, Regigigas, Regidrago, Landorus, Diancie, Zygarde (9 items)
11. **Flying/Wind** - Ho-Oh, Tornadus, Raikou, Latias, Latios (5 items)
12. **Psychic/Mystic** - Azelf, Mesprit, Uxie, Tapu Lele, Meloetta (5 items)
13. **Fighting/Combat** - Kubfu, Keldeo, Cobalion (3 items)
14. **Ruin/Cursed** - Ting-Lu, Chien-Pao, Wo-Chien, Chi-Yu (4 items)
15. **Rare/Event** - Mewtwo, Calyrex, Victini, Manaphy, Enamorus (5 items)

**Total** : 79 items legendaires et mythiques repartis dans 15 categories

**Nouveaux fichiers crees** :
- `loot_table/myths_and_legends/legendaries_fire.json`
- `loot_table/myths_and_legends/legendaries_water.json`
- `loot_table/myths_and_legends/legendaries_ice.json`
- `loot_table/myths_and_legends/legendaries_electric.json`
- `loot_table/myths_and_legends/legendaries_dragon.json`
- `loot_table/myths_and_legends/legendaries_forest.json`
- `loot_table/myths_and_legends/legendaries_dark.json`
- `loot_table/myths_and_legends/legendaries_cosmic.json`
- `loot_table/myths_and_legends/legendaries_steel.json`
- `loot_table/myths_and_legends/legendaries_rock.json`
- `loot_table/myths_and_legends/legendaries_flying.json`
- `loot_table/myths_and_legends/legendaries_psychic.json`
- `loot_table/myths_and_legends/legendaries_fighting.json`
- `loot_table/myths_and_legends/legendaries_ruin.json`
- `loot_table/myths_and_legends/legendaries_rare.json`

**Fonctionnement technique** :
- Les coffres (t1-t9) referent `academy:myths_and_legends/legendaries` (weight 1 + air 49 = 1/50)
- `legendaries.json` dispatche vers les 15 sous-tables avec des conditions `minecraft:location_check` par biome
- Seules les categories correspondant au biome du coffre sont eligibles
- La categorie "Rare/Event" (Mewtwo, Calyrex, Victini, Manaphy, Enamorus) est disponible partout (fallback)
- Les gyms utilisent le meme systeme de dispatch (1/20 chance) et beneficient du filtrage par biome

**Mapping biome -> categories** :
- Deserts/Badlands/Nether : Fire, Ruin, Rock, Steel
- Oceans/Rivieres/Plages : Water
- Neige/Glaciers : Ice
- Plaines/Meadows : Electric, Flying, Steel, Fighting
- End/Deep Dark : Dragon, Cosmic
- Forets/Jungles/Taiga : Forest
- Dark Forest/Swamp/Nether : Dark
- Montagnes/Peaks : Flying, Dragon, Rock, Ice
- Grottes (Lush/Dripstone) : Rock, Psychic
- Mushroom Fields : Water, Cosmic, Psychic
- Cherry Grove/Flower Forest : Forest, Flying, Psychic

### Unicite des legendaires

| Parametre | Avant | Apres |
|-----------|-------|-------|
| `unique` | false | **true** |

**Fichier** : `config/academy/legendary_items.json`

Chaque item legendaire (Orbe Adamant, Orbe Bleu, DNA Splicer, etc.) ne peut etre obtenu qu'**une seule fois par monde**. Si un joueur obtient l'Adamant Orb, aucun autre joueur ne pourra en trouver. Cela rend chaque drop legendaire unique et precieux.

**Liste des 79 items legendaires concernes** : Adamant Orb, Blue Orb, DNA Splicer, Eon Tickets, Griseous Orb, Jade Orb, Lustrous Orb, Red Orb, Rusted Shield/Sword, Dr. Fuji's Diary, Rainbow/Silver Wing, Violet/Scarlet Book, Cocoon of Destruction, Sapling of Life, Reveal Glass (x4), Clear Bell (x3), Tidal Bell (x3), Dark/Light Stone, Teal Mask, Lunar Feather, Magma Stone, Totems (Fini, Koko, Lele, Bulu), Grassland Blade, Ironwill Sword, Lillie's Bag, Necro Prism, Type: Null Mask, Eternatus Core, Kubfu's Band, Tablets (Plasma, Scaly, Stone, Ice, Steel, Ancient), Prismatic Shell, Reins of Unity, Azelf Fang, Mesprit Plume, Uxie Claw, Iceroot/Shaderoot Carrot, Sun/Moon Flute, Cavern Shield, Tablets/Sword/Vessel/Beads of Ruin.

### Comment fonctionnent les items legendaires ?

1. Un item legendaire est trouve dans un coffre (selon les taux ci-dessus)
2. L'item `academy:legendary_placeholder` est donne, qui se transforme en un item legendaire aleatoire
3. L'item legendaire est consomme quand utilise pour invoquer le Pokemon legendaire correspondant
4. Le broadcast MythsAndLegends annonce le spawn a tous les joueurs

---

## 4. Evenements Lunaires (Enhanced Celestials)

| Lune | Effet | Multiplicateur |
|------|-------|----------------|
| Blue Moon | Boost Shiny | x10 |
| Blood Moon | Boost IVs | x2 |
| Harvest Moon | Boost EXP Share | x4 |
| **Aurora Moon** | **Spawn Pokemon rares** | **x5** (etait x4) |
| Super Blue Moon | Boost Shiny | x16 |
| Super Blood Moon | Boost IVs | x3 |
| Super Harvest Moon | Boost EXP Share | x6 |
| Super Aurora Moon | Spawn Pokemon rares | x6 |

**Fichier** : `config/academy/ec_cobblemon.json`

> Les previsions lunaires sont visibles sur 10 jours en avance (`forecastDayView: 10`).

---

## 5. Annonces en Chat

### Spawn Alerts (cote client)
| Parametre | Avant | Apres |
|-----------|-------|-------|
| `alertAllShinies` | false | **true** |
| `alertAllLegendaries` | deja true | true |
| `alertAllMythicals` | deja true | true |
| `alertAllUltraBeasts` | deja true | true |
| `alertAllParadox` | deja true | true |

**Fichier** : `config/cobblemon-spawn-alerts/main.json`

### Spawn Alerts (cote serveur)
| Parametre | Avant | Apres |
|-----------|-------|-------|
| `alertShinies` | false | **true** |
| `alertLegendaries` | deja true | true |
| `alertMythicals` | deja true | true |
| `alertUltraBeasts` | deja true | true |

**Fichier** : `config/cobblemon-spawn-alerts/server.json`

### Informations affichees dans l'alerte
| Info | Mode |
|------|------|
| Biome | Affiche dans le message |
| Joueur le plus proche | **Affiche dans le message** |
| Niveau | Desactive |
| Coordonnees | Desactive |

**Fichier** : `config/cobblemon-spawn-alerts/pokemon.json`

### Broadcasts MythsAndLegends
| Parametre | Avant | Apres |
|-----------|-------|-------|
| `isBroadcastEnabled` | false | **true** |
| Ultra Beasts | false | **true** |
| Shiny | false | **true** |
| Legendaires | deja true | true |
| Mythiques | deja true | true |
| Localisation | deja true | true |
| Niveau | deja true | true |

**Fichier** : `config/MythsAndLegends/config.toml`

---

## 6. Mega Evolution / Teralization / Dynamax / Z-Moves

### Tera Shard Drop
| Parametre | Avant | Apres |
|-----------|-------|-------|
| `disableTeraShardDrop` | true (pas de drop) | **false (drop actif)** |

**Fichier** : `config/mega_showdown-mega_showdown-common.toml`

Les Pokemon sauvages peuvent maintenant drop des Tera Shards en combat.

### Structures Mega Showdown reactivees
- **Wishing Weald** : Foret des Voeux, necessite pour le Dynamax (Power Spot, range 20 blocs)
- **Archaeological Site** : Contient des Mega Stones
- **Mega Site** : Autre source de Mega Stones
- **Megaroid** : Meteorite avec items Mega

### Recap des fonctionnalites actives
| Fonctionnalite | Statut |
|-----------------|--------|
| Mega Evolution | Active |
| Dynamax/Gigamax | Active (pres d'un Power Spot uniquement) |
| Teralization | Active |
| Z-Moves | Active |
| Power Spot Range | 20 blocs |

---

## 7. Niveaux des Pokemon Sauvages

Les Pokemon sauvages utilisent un systeme de niveau base sur la distance au spawn :

| Distance du spawn | Niveau min | Niveau max |
|-------------------|------------|------------|
| 0 blocs | 0 | 10 |
| 1 000 blocs | 0 | 15 |
| 2 000 blocs | 0 | 25 |
| 3 000 blocs | 0 | 35 |
| 5 000 blocs | 0 | 45 |
| 7 000 blocs | 0 | 55 |
| 10 000+ blocs | 0 | 70 |

**Fichier** : `config/academy/pokemon_spawn.json`

> Le level cap absolu est 100 (`maxPokemonLevel: 100` dans cobblemon/main.json).

---

## 8. Autres Parametres Utiles (inchanges)

| Parametre | Valeur | Fichier |
|-----------|--------|---------|
| Taux Ultra Beasts (Wormhole) | 1/4000 | `cobblemon_ultrabeasts_config.json` |
| Chance Alpha spawn | 0.005% | `cobblemonalphas/config.json` |
| Alpha shiny odds | 1/128 | `cobblemonalphas/config.json` |
| Breeding Shiny (Masuda) | x4 | `cobbreeding/main.json` |
| EXP Share multiplier | x0.5 | `cobblemon/main.json` |
| Lucky Egg multiplier | x1.5 | `cobblemon/main.json` |
| Pokemon par chunk | 1.0 | `cobblemon/main.json` |
| Spawners de mobs | Desactives (count: 0) | `spawner_control-common.json` |
| Boxes PC | 50 | `cobblemon/main.json` |
| PvP EXP | Active | `cobblemon/main.json` |
| Tera Type Rate | 1/20 | `cobblemon/main.json` |

---

## Resume des Fichiers Modifies

| Fichier | Modifications |
|---------|---------------|
| `config/cobblemon/main.json` | shinyRate 3072 -> 2048 |
| `config/MoreSparkles/items.json` | Shiny Charm multiplier 1.1 -> 1.5 |
| `config/academy/ec_cobblemon.json` | Aurora Moon x4 -> x5 |
| `config/cobblemon-spawn-alerts/main.json` | alertAllShinies active |
| `config/cobblemon-spawn-alerts/server.json` | alertShinies active |
| `config/cobblemon-spawn-alerts/pokemon.json` | nearestPlayer dans le message |
| `config/MythsAndLegends/config.toml` | Broadcasts actives (UB, Shiny) |
| `config/mega_showdown-mega_showdown-common.toml` | Tera Shard drop reactive |
| `config/structurify.json` | Modifier 1.3, 22 structures reactivees (toutes sauf stronghold_big) |
| `loot_table/basic/t1.json` a `t9.json` | Pools uniformes : pokeballs (1/3, 1/5, 1/10, 1/50), fossiles (1/30 + 10% special), cles gym (1/30), TMs (1/15), pokeblocks (1/30), legendaire (1/50), 6x mega showdown (1/50), booster (1/20) |
| `loot_table/basic_underground/t1.json` a `t9.json` | Memes pools uniformes que basic, fossiles a 1/15 |
| `loot_table/basic_gym/t0.json` a `t10.json` | Legendaire uniforme 1/20 (weight empty: 19) + TMs pool ajoute (1/15) |
| `loot_table/myths_and_legends/legendaries.json` | Dispatch par biome avec conditions `minecraft:location_check` vers 15 sous-tables |
| `loot_table/myths_and_legends/legendaries_*.json` | 15 nouveaux fichiers thematiques crees (fire, water, ice, electric, dragon, forest, dark, cosmic, steel, rock, flying, psychic, fighting, ruin, rare) |
| `config/academy/legendary_items.json` | unique: true |
