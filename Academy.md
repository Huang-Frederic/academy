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

#### Alpha Dens (Cobblemon Alphas) - NE FONCTIONNENT PAS
- `cobblemonalphas:alpha_den_underground` - Taniere souterraine d'Alphas (**ne spawne pas d'Alphas**)
- `cobblemonalphas:plains_den` - Taniere de plaines (**ne spawne pas d'Alphas**)

> **Note** : Ces structures existent dans le monde mais les Alphas ne spawnent pas dedans d'après les tests. Cette feature ne marche pas actuellement sur le serveur.

#### Mega Showdown
- `mega_showdown:archaeological_site` - Site archeologique (Mega Stones)
- `mega_showdown:mega_site` - Site Mega
- `mega_showdown:megaroid` - Meteorite Mega
- `mega_showdown:wishing_weald` - Foret des Voeux (Power Spot Dynamax)

#### Rad Gyms (18 types)
Les **cles de gym** (gym keys) sont trouvees dans les coffres du monde (drop table). Il n'y a pas de structures de gym a trouver dans le monde - utilisez simplement la cle en faisant **clic droit** pour vous teleporter dans l'arene correspondante.

Types disponibles : `bug`, `dark`, `dragon`, `electric`, `fairy`, `fighting`, `fire`, `flying`, `ghost`, `grass`, `ground`, `ice`, `normal`, `poison`, `psychic`, `rock`, `steel`, `water`

#### Minecraft vanilla
| Structure | Avant | Apres |
|-----------|-------|-------|
| Mineshafts | 0.0 (desactive) | **0.4** |
| Buried Treasures | 0.0 (desactive) | **0.3** |
| Trial Chambers | desactive | **reactive** |

#### Eternal Starlight 
- `eternal_starlight:cursed_garden` - Jardin Maudit
- `eternal_starlight:golem_forge` - Forge de Golem
- `eternal_starlight:portal_ruins_cold` - Ruines de Portail (froid)
- `eternal_starlight:portal_ruins_common` - Ruines de Portail (commun)
- `eternal_starlight:portal_ruins_desert` - Ruines de Portail (desert)
- `eternal_starlight:portal_ruins_forest` - Ruines de Portail (foret)
- `eternal_starlight:portal_ruins_jungle` - Ruines de Portail (jungle)
- `eternal_starlight:stranghoul_den` - Taniere de Stranghoul

#### MNS 
- `mns:copper_tower` - Tour de Cuivre

#### MSS 
- `mss:arena` - Arene de combat
- `mss:calcite_house` - Maison de Calcite
- `mss:volcano` - Volcan

#### MVS 
- `mvs:carts/cart` - Chariot
- `mvs:carts/large_cart_1` - Grand Chariot 1
- `mvs:carts/large_cart_2` - Grand Chariot 2
- `mvs:carts/medium_bamboo_cart` - Chariot Bambou Moyen
- `mvs:cathedral` - Cathedrale
- `mvs:houses/large_warped_tower` - Grande Tour Tordue

#### Trek 
- `trek:overworld/rare/villager_castle` - Chateau Villageois (rare)
- `trek:overworld/very_rare/coves` - Criques (tres rare)

#### ATI 
- `ati_structures:gnome_hut` - Hutte de Gnome

### Structures restant desactivees
- `minecraft:stronghold_big` (redondant avec minecraft:strongholds)

---

## 3. Items Legendaires & Loot Tables

### Systeme de tiers par distance

Les coffres du monde utilisent un systeme de tiers base sur la distance au spawn. Plus tu t'eloignes, meilleur est le loot.

#### Taux de drop d'item legendaire par tier 

| Tier | Distance approx. | Chance legendaire |
|------|------------------|-------------------|
| **t0** | Spawn | Aucune |
| **t1+** | ~1000+ blocs | **1/100** |

> **Changement majeur** : Le taux de drop legendaire est maintenant **constant a 1/100 par coffre** pour tous les tiers a partir du t1. Seul le t0 (spawn) ne contient pas de legendaire.

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
| Fossiles | **1/30** | Pool groupe: fossiles normaux (90%) + Shiny/HA/MaxIV (10%) |
| Cles de gym | **1/50** | Toutes les 18 cles de type |
| CT/TMs | **1/30** | Tous les TMs disponibles |
| Pokedolls | **1/30** | Pool groupe: Common(60%), Uncommon(30%), Rare(4%), Epic(3%), Legendary(2%), Shiny(1%) |
| Legendaires | **1/100** | Items legendaires (systeme par biome) |
| Mega/Tera/Z/Master | **1/50** | Pool groupe: Pierre Mega, Fragment Tera, Cristal Z, ou Master Ball (25% chacun) |
| Forms (Silvally/Rotom/Arceus) | **1/50** | Pool groupe: Memoire Silvally, Forme Rotom, ou Plaque Arceus (33% chacun) |
| Booster Pack | **1/30** | Pack booster |

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

### Pools groupes 

#### Pool Mega/Tera/Z/Master (`pool_mega_tera_z_master.json`)
- 1 seul roll a **1/50**
- Contenu : Mega Stone (25%), Tera Shard (25%), Z-Crystal (25%), Master Ball (25%)
- **Fichier cree** : `loot_table/megashowdown/pool_mega_tera_z_master.json`

#### Pool Forms (`pool_forms.json`)
- 1 seul roll a **1/50**
- Contenu : Silvally Memory (33%), Rotom Form (33%), Arceus Plate (33%)
- **Fichier cree** : `loot_table/megashowdown/pool_forms.json`

#### Pool Fossiles (`fossils_pool.json`)
- 1 seul roll a **1/30** (ou 1/15 underground)
- Contenu : Fossiles normaux (90%), Shiny Fossil (3.33%), HA Fossil (3.33%), Max IV Fossil (3.33%)
- **Fichier cree** : `loot_table/cobblemon/fossils_pool.json`

> **Resultat** : Les taux de drop sont maintenant precis et correspondent aux intentions de design. Mega/Tera/Forms = 2x 1/50 = ~4% total

### Loot des Gyms (MODIFIE - taux progressifs t1-t9)

Les gymnases Rad Gyms utilisent maintenant des **taux de drop progressifs** qui s'ameliorent du t1 au t9 :

| Tier | Legendaire | Mega/Tera/Z/Arceus (chaque pool) | Booster Pack |
|------|------------|----------------------------------|--------------|
| **t1** | 1/100 | 1/50 | 1/3 |
| **t2** | 1/90 | 1/45 | 1/2 |
| **t3** | 1/79 | 1/40 | 1/2 |
| **t4** | 1/69 | 1/35 | 1/2 |
| **t5** | 1/59 | 1/30 | 1/1 |
| **t6** | 1/49 | 1/25 | 1/1 |
| **t7** | 1/44 | 1/20 | 1/1 |
| **t8** | 1/39 | 1/15 | Garanti |
| **t9** | 1/30 | 1/10 | Garanti |

**Nouveau** : Un pool de **TMs/CTs** a ete ajoute a tous les gyms (t1-t9) avec un taux uniforme de **1/30** (weight 1, empty 29).

**Fichiers modifies** : `loot_table/basic_gym/t1.json` a `t9.json`

**Note technique** : Les taux progressifs utilisent une interpolation lineaire entre les valeurs t1 et t9.

### Systeme de distribution par biome/theme

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

### Frequence des lunes (MODIFIE)

Les evenements lunaires ont ete configures pour avoir environ **1 evenement tous les 4 jours** :

| Lune | Effet | Multiplicateur | Chance | Min Nuits |
|------|-------|----------------|--------|-----------|
| Blue Moon | Boost Shiny | x10 | 8.3% | 4 |
| Blood Moon | Boost IVs | x2 | 8.3% | 4 |
| Harvest Moon | Boost EXP Share | x4 | 8.3% | 4 |
| **Aurora Moon** | **Spawn Pokemon rares** | **x5** (etait x4) | 8.3% | 4 |
| Super Blue Moon | Boost Shiny | x16 | 4% | 10 |
| Super Blood Moon | Boost IVs | x3 | 4% | 10 |
| Super Harvest Moon | Boost EXP Share | x6 | 4% | 10 |

**Fichiers modifies** : `event/blue_moon.json`, `blood_moon.json`, `harvest_moon.json`, `aurora_moon.json`, `super_blue_moon.json`, `super_blood_moon.json`, `super_harvest_moon.json`

**Fichier de config** : `config/academy/ec_cobblemon.json`

> Les previsions lunaires sont visibles sur 10 jours en avance (`forecastDayView: 10`).

**Calcul de frequence** :
- 4 lunes normales a 8.3% chance tous les 4 jours minimum = ~33% d'avoir une lune normale tous les 4 jours
- Soit environ **1 lune normale tous les 12 jours** (par type)
- Les super lunes a 4% avec 10 jours minimum = environ **1 super lune tous les 25 jours** (par type)
- **Resultat global : ~1 evenement lunaire tous les 4 jours** en comptant toutes les lunes

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
| `isBroadcastEnabled` | true | **false (DESACTIVE)** |

**Fichier** : `config/MythsAndLegends/config.toml`

> **Note** : Les broadcasts MythsAndLegends sont desactives pour eviter les doublons. Seul Cobblemon Spawn Alerts annonce les spawns naturels (sans coordonnees exactes).

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

## 8. Ride Pokemon (CobbleRide)

### Selle non requise
| Parametre | Avant | Apres |
|-----------|-------|-------|
| `isSaddleRequired` | true | **false** |

**Fichier** : `config/cobbleride/config.json`

> Les joueurs peuvent maintenant monter sur leurs Pokemon sans avoir besoin de selle.

---

## 9. Autres Parametres Utiles (inchanges)

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
| `config/cobbleride/config.json` | isSaddleRequired false (ride sans selle) |
| `config/cobblemon-spawn-alerts/pokemon.json` | nearestPlayer dans le message |
| `config/MythsAndLegends/config.toml` | isBroadcastEnabled desactive (eviter doublons avec Cobblemon Spawn Alerts) |
| `config/mega_showdown-mega_showdown-common.toml` | Tera Shard drop reactive |
| `config/structurify.json` | Modifier 1.3, 22 structures reactivees (toutes sauf stronghold_big) |
| `loot_table/basic/t1.json` a `t9.json` | Pools uniformes : pokeballs (1/3, 1/5, 1/10, 1/50), fossiles pool groupe (1/30 avec 90/10), cles gym (1/50), TMs (1/30), pokedolls pool groupe (1/30 avec 60/30/4/3/2/1), legendaire (1/100), mega/tera/z/master pool groupe (1/50), forms pool groupe (1/50), booster (1/30) |
| `loot_table/basic_underground/t1.json` a `t9.json` | Memes pools uniformes que basic, fossiles pool groupe a 1/15 (double rate) |
| `loot_table/basic_gym/t1.json` a `t9.json` | Taux progressifs : legendaire (1/100 -> 1/30), mega/tera/z/arceus (1/50 -> 1/10), booster (1/3 -> garanti) + TMs pool uniforme (1/30) |
| `loot_table/megashowdown/pool_mega_tera_z_master.json` | CREE - Pool groupe : Mega Stone, Tera Shard, Z-Crystal, Master Ball (25% chacun) |
| `loot_table/megashowdown/pool_forms.json` | CREE - Pool groupe : Silvally Memory, Rotom Form, Arceus Plate (33% chacun) |
| `loot_table/cobblemon/fossils_pool.json` | CREE - Pool groupe : Fossiles normaux (90%), Shiny/HA/MaxIV (10%) |
| `loot_table/myths_and_legends/legendaries.json` | Dispatch par biome avec conditions `minecraft:location_check` vers 15 sous-tables |
| `loot_table/myths_and_legends/legendaries_*.json` | 15 nouveaux fichiers thematiques crees (fire, water, ice, electric, dragon, forest, dark, cosmic, steel, rock, flying, psychic, fighting, ruin, rare) |
| `config/academy/legendary_items.json` | unique: true |
| `event/blue_moon.json` | chance: 0.083, min_number_of_nights_between: 4 |
| `event/blood_moon.json` | chance: 0.083, min_number_of_nights_between: 4 |
| `event/harvest_moon.json` | chance: 0.083, min_number_of_nights_between: 4 |
| `event/aurora_moon.json` | chance: 0.083, min_number_of_nights_between: 4 |
| `event/super_blue_moon.json` | chance: 0.04, min_number_of_nights_between: 10 |
| `event/super_blood_moon.json` | chance: 0.04, min_number_of_nights_between: 10 |
| `event/super_harvest_moon.json` | chance: 0.04, min_number_of_nights_between: 10 |
