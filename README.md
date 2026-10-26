# One Piece Wanted Posters and Bounties

**120 One Piece wanted posters** with the latest bounties, crews and official names in **7 languages**: free printable posters on [onepieceposter.com](https://onepieceposter.com/one-piece-posters/) and the data behind them as JSON and CSV.

- 98 characters with a revealed bounty, 22 with a bounty whose amount was never revealed (`"bounty": null`, shown as ฿ ???)
- 14 groups: Straw Hats, Emperors, Warlords, Worst Generation, Roger Pirates, Whitebeard Pirates and more
- Names and nicknames in English, Spanish, French, German, Portuguese (Brazil), Italian and Indonesian, checked against each language's One Piece wiki (official manga translations such as Ruffy, Rufy, Baggy)
- Ordered from the most popular character to the least

Want a poster of one of them with your own name? Make it free in the [One Piece wanted poster maker](https://onepieceposter.com/).

## Files

| File | What it holds |
|---|---|
| [`data/characters.json`](data/characters.json) | Everything: characters, group names in 7 languages, metadata |
| [`data/characters.csv`](data/characters.csv) | One row per character, a column per language (`name_de`, `nickname_fr`, ...) |
| [`data/groups.json`](data/groups.json) | Group keys and their names in 7 languages |

## Fields

| Field | Example | Notes |
|---|---|---|
| `slug` | `monkey-d-luffy` | stable id |
| `name` | `Monkey D. Luffy` | name as printed on the poster |
| `bounty` | `3000000000` | in Berries (Belly); `null` when the amount was never revealed |
| `bounty_known` | `true` | |
| `groups` | `["straw-hats", "emperors"]` | keys of `groups.json` |
| `names` | `{"de": "Monkey D. Ruffy", "it": "Monkey D. Rufy"}` | official name in each language; the English one where the translation keeps it |
| `nicknames` | `{"en": "Straw Hat Luffy", "fr": "Luffy au Chapeau de paille"}` | official epithet; `null` where the language has none |
| `poster` | `https://onepieceposter.com/one-piece-posters/#monkey-d-luffy` | the character's wanted poster |
| `make_poster` | `https://onepieceposter.com/?poster=monkey-d-luffy` | opens the poster maker with this poster |
| `popularity_rank` | `1` | order of the gallery, most popular first |

## Use it

JavaScript:

```js
const url = 'https://raw.githubusercontent.com/Maksis72/one-piece-wanted-posters/main/data/characters.json'
const { characters } = await (await fetch(url)).json()
const top = characters.filter(c => c.bounty_known).sort((a, b) => b.bounty - a.bounty).slice(0, 10)
```

Python:

```python
import csv
with open("data/characters.csv", encoding="utf-8") as f:
    straw_hats = [r for r in csv.DictReader(f) if "straw-hats" in r["groups"].split("|")]
```

## Characters

| # | Character | Nickname | Bounty | Groups | Poster |
|---:|---|---|---:|---|---|
| 1 | Monkey D. Luffy | Straw Hat Luffy | ฿&nbsp;3,000,000,000 | Straw Hats, Emperors, Worst Generation | [poster](https://onepieceposter.com/one-piece-posters/#monkey-d-luffy) |
| 2 | Roronoa Zoro | Pirate Hunter Zoro | ฿&nbsp;1,111,000,000 | Straw Hats, Worst Generation | [poster](https://onepieceposter.com/one-piece-posters/#roronoa-zoro) |
| 3 | Nico Robin | Devil Child | ฿&nbsp;930,000,000 | Straw Hats | [poster](https://onepieceposter.com/one-piece-posters/#nico-robin) |
| 4 | Nami | Cat Burglar | ฿&nbsp;366,000,000 | Straw Hats | [poster](https://onepieceposter.com/one-piece-posters/#nami) |
| 5 | Boa Hancock | Snake Princess | ฿&nbsp;1,659,000,000 | Warlords | [poster](https://onepieceposter.com/one-piece-posters/#boa-hancock) |
| 6 | Vinsmoke Sanji | Black Leg | ฿&nbsp;1,032,000,000 | Straw Hats | [poster](https://onepieceposter.com/one-piece-posters/#vinsmoke-sanji) |
| 7 | Tony Tony Chopper | Cotton Candy Lover | ฿&nbsp;1,000 | Straw Hats | [poster](https://onepieceposter.com/one-piece-posters/#tony-tony-chopper) |
| 8 | Kaido | Kaido of the Beasts | ฿&nbsp;4,611,100,000 | Emperors, Beasts Pirates | [poster](https://onepieceposter.com/one-piece-posters/#kaido) |
| 9 | Usopp | God Usopp | ฿&nbsp;500,000,000 | Straw Hats | [poster](https://onepieceposter.com/one-piece-posters/#usopp) |
| 10 | Trafalgar Law | Surgeon of Death | ฿&nbsp;3,000,000,000 | Warlords, Worst Generation | [poster](https://onepieceposter.com/one-piece-posters/#trafalgar-law) |
| 11 | Portgas D. Ace | Fire Fist Ace | ฿&nbsp;550,000,000 | Whitebeard Pirates | [poster](https://onepieceposter.com/one-piece-posters/#portgas-d-ace) |
| 12 | Donquixote Doflamingo | Heavenly Yaksha | ฿&nbsp;340,000,000 | Warlords, Donquixote Pirates | [poster](https://onepieceposter.com/one-piece-posters/#donquixote-doflamingo) |
| 13 | Loki | Accursed Prince | ฿&nbsp;2,600,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#loki) |
| 14 | Brook | Soul King | ฿&nbsp;383,000,000 | Straw Hats | [poster](https://onepieceposter.com/one-piece-posters/#brook) |
| 15 | Sabo | Flame Emperor | ฿&nbsp;602,000,000 | Revolutionary Army | [poster](https://onepieceposter.com/one-piece-posters/#sabo) |
| 16 | Charlotte Linlin | Big Mom | ฿&nbsp;4,388,000,000 | Emperors, Big Mom Pirates | [poster](https://onepieceposter.com/one-piece-posters/#charlotte-linlin) |
| 17 | Edward Newgate | Whitebeard | ฿&nbsp;5,046,000,000 | Emperors, Whitebeard Pirates | [poster](https://onepieceposter.com/one-piece-posters/#edward-newgate) |
| 18 | Gol D. Roger | Pirate King | ฿&nbsp;5,564,800,000 | Roger Pirates | [poster](https://onepieceposter.com/one-piece-posters/#gol-d-roger) |
| 19 | Dracule Mihawk | Hawk Eyes Mihawk | ฿&nbsp;3,590,000,000 | Warlords, Cross Guild | [poster](https://onepieceposter.com/one-piece-posters/#dracule-mihawk) |
| 20 | Monkey D. Dragon | Rebellious Dragon | ฿&nbsp;??? | Revolutionary Army | [poster](https://onepieceposter.com/one-piece-posters/#monkey-d-dragon) |
| 21 | Marshall D. Teach | Blackbeard | ฿&nbsp;3,996,000,000 | Emperors, Warlords, Worst Generation, Blackbeard Pirates | [poster](https://onepieceposter.com/one-piece-posters/#marshall-d-teach) |
| 22 | Charlotte Katakuri | Sweet Commander | ฿&nbsp;1,057,000,000 | Big Mom Pirates | [poster](https://onepieceposter.com/one-piece-posters/#charlotte-katakuri) |
| 23 | Franky | Iron Man Franky | ฿&nbsp;394,000,000 | Straw Hats | [poster](https://onepieceposter.com/one-piece-posters/#franky) |
| 24 | Crocodile | Sir Crocodile | ฿&nbsp;1,965,000,000 | Warlords, Cross Guild, Baroque Works | [poster](https://onepieceposter.com/one-piece-posters/#crocodile) |
| 25 | Bon Clay | Mr. 2 | ฿&nbsp;32,000,000 | Baroque Works | [poster](https://onepieceposter.com/one-piece-posters/#bon-clay) |
| 26 | Shanks | Red-Haired Shanks | ฿&nbsp;4,048,900,000 | Emperors, Roger Pirates, Red Hair Pirates | [poster](https://onepieceposter.com/one-piece-posters/#shanks) |
| 27 | Rocks D. Xebec |  | ฿&nbsp;??? |  | [poster](https://onepieceposter.com/one-piece-posters/#rocks-d-xebec) |
| 28 | Jewelry Bonney | Big Eater | ฿&nbsp;320,000,000 | Worst Generation | [poster](https://onepieceposter.com/one-piece-posters/#jewelry-bonney) |
| 29 | Buggy | Buggy the Clown | ฿&nbsp;3,189,000,000 | Emperors, Warlords, Roger Pirates, Cross Guild | [poster](https://onepieceposter.com/one-piece-posters/#buggy) |
| 30 | Jinbe | Knight of the Sea | ฿&nbsp;1,100,000,000 | Straw Hats, Warlords | [poster](https://onepieceposter.com/one-piece-posters/#jinbe) |
| 31 | Alvida | Iron Mace | ฿&nbsp;5,000,000 | Cross Guild | [poster](https://onepieceposter.com/one-piece-posters/#alvida) |
| 32 | Gecko Moria |  | ฿&nbsp;320,000,000 | Warlords | [poster](https://onepieceposter.com/one-piece-posters/#gecko-moria) |
| 33 | Arlong | Arlong the Saw | ฿&nbsp;20,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#arlong) |
| 34 | King | King the Conflagration | ฿&nbsp;1,390,000,000 | Beasts Pirates | [poster](https://onepieceposter.com/one-piece-posters/#king) |
| 35 | Galdino | Mr. 3 | ฿&nbsp;24,000,000 | Baroque Works | [poster](https://onepieceposter.com/one-piece-posters/#galdino) |
| 36 | Eustass Kid | Captain Kid | ฿&nbsp;3,000,000,000 | Worst Generation | [poster](https://onepieceposter.com/one-piece-posters/#eustass-kid) |
| 37 | Emporio Ivankov | Okama King | ฿&nbsp;100,000,000 | Revolutionary Army | [poster](https://onepieceposter.com/one-piece-posters/#emporio-ivankov) |
| 38 | Marco | Marco the Phoenix | ฿&nbsp;1,374,000,000 | Whitebeard Pirates | [poster](https://onepieceposter.com/one-piece-posters/#marco) |
| 39 | Mikita | Miss Valentine | ฿&nbsp;7,500,000 | Baroque Works | [poster](https://onepieceposter.com/one-piece-posters/#mikita) |
| 40 | Marianne | Miss Goldenweek | ฿&nbsp;29,000,000 | Baroque Works | [poster](https://onepieceposter.com/one-piece-posters/#marianne) |
| 41 | Queen | Queen the Plague | ฿&nbsp;1,320,000,000 | Beasts Pirates | [poster](https://onepieceposter.com/one-piece-posters/#queen) |
| 42 | Crocus |  | ฿&nbsp;??? | Roger Pirates | [poster](https://onepieceposter.com/one-piece-posters/#crocus) |
| 43 | Silvers Rayleigh | Dark King | ฿&nbsp;??? | Roger Pirates | [poster](https://onepieceposter.com/one-piece-posters/#silvers-rayleigh) |
| 44 | Kozuki Oden | Idiot Lord | ฿&nbsp;??? | Roger Pirates, Whitebeard Pirates | [poster](https://onepieceposter.com/one-piece-posters/#kozuki-oden) |
| 45 | Don Krieg |  | ฿&nbsp;17,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#don-krieg) |
| 46 | Kuro | Kuro of a Hundred Plans | ฿&nbsp;16,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#kuro) |
| 47 | Koala |  | ฿&nbsp;??? | Revolutionary Army | [poster](https://onepieceposter.com/one-piece-posters/#koala) |
| 48 | Señor Pink |  | ฿&nbsp;58,000,000 | Donquixote Pirates | [poster](https://onepieceposter.com/one-piece-posters/#senor-pink) |
| 49 | Caesar Clown | Master | ฿&nbsp;300,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#caesar-clown) |
| 50 | Gem | Mr. 5 | ฿&nbsp;10,000,000 | Baroque Works | [poster](https://onepieceposter.com/one-piece-posters/#gem) |
| 51 | Bellamy | Bellamy the Hyena | ฿&nbsp;195,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#bellamy) |
| 52 | Cavendish | Cavendish of the White Horse | ฿&nbsp;330,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#cavendish) |
| 53 | Black Maria |  | ฿&nbsp;480,000,000 | Beasts Pirates | [poster](https://onepieceposter.com/one-piece-posters/#black-maria) |
| 54 | Bepo |  | ฿&nbsp;1,500 |  | [poster](https://onepieceposter.com/one-piece-posters/#bepo) |
| 55 | Benn Beckman |  | ฿&nbsp;??? | Red Hair Pirates | [poster](https://onepieceposter.com/one-piece-posters/#benn-beckman) |
| 56 | Daz Bonez | Mr. 1 | ฿&nbsp;75,000,000 | Baroque Works | [poster](https://onepieceposter.com/one-piece-posters/#daz-bonez) |
| 57 | Foxy | Silver Fox | ฿&nbsp;24,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#foxy) |
| 58 | Ginny |  | ฿&nbsp;190,000,000 | Revolutionary Army | [poster](https://onepieceposter.com/one-piece-posters/#ginny) |
| 59 | Killer | Massacre Soldier | ฿&nbsp;200,000,000 | Worst Generation | [poster](https://onepieceposter.com/one-piece-posters/#killer) |
| 60 | Ulti |  | ฿&nbsp;400,000,000 | Beasts Pirates | [poster](https://onepieceposter.com/one-piece-posters/#ulti) |
| 61 | Yasopp | Chaser | ฿&nbsp;??? | Red Hair Pirates | [poster](https://onepieceposter.com/one-piece-posters/#yasopp) |
| 62 | Izo |  | ฿&nbsp;510,000,000 | Whitebeard Pirates | [poster](https://onepieceposter.com/one-piece-posters/#izou) |
| 63 | Charlotte Lola | Marriage Proposal Lola | ฿&nbsp;24,000,000 | Big Mom Pirates | [poster](https://onepieceposter.com/one-piece-posters/#charlotte-lola) |
| 64 | Caribou | Wet-Haired Caribou | ฿&nbsp;210,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#caribou) |
| 65 | Fisher Tiger | The Adventurer | ฿&nbsp;230,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#fisher-tiger) |
| 66 | Pedro | Pedro of the Treetops | ฿&nbsp;382,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#pedro) |
| 67 | Pica |  | ฿&nbsp;99,000,000 | Donquixote Pirates | [poster](https://onepieceposter.com/one-piece-posters/#pica) |
| 68 | X Drake | Red Flag | ฿&nbsp;222,000,000 | Worst Generation | [poster](https://onepieceposter.com/one-piece-posters/#x-drake) |
| 69 | Charlotte Smoothie |  | ฿&nbsp;932,000,000 | Big Mom Pirates | [poster](https://onepieceposter.com/one-piece-posters/#charlotte-smoothie) |
| 70 | Jack | Jack the Drought | ฿&nbsp;1,000,000,000 | Beasts Pirates | [poster](https://onepieceposter.com/one-piece-posters/#jack) |
| 71 | Douglas Bullet | Demon Heir | ฿&nbsp;??? | Roger Pirates | [poster](https://onepieceposter.com/one-piece-posters/#douglas-bullet) |
| 72 | Catarina Devon | Crescent Moon Hunter | ฿&nbsp;??? | Blackbeard Pirates | [poster](https://onepieceposter.com/one-piece-posters/#catarina-devon) |
| 73 | Basil Hawkins | Magician | ฿&nbsp;320,000,000 | Worst Generation | [poster](https://onepieceposter.com/one-piece-posters/#basil-hawkins) |
| 74 | Edward Weevil |  | ฿&nbsp;480,000,000 | Warlords | [poster](https://onepieceposter.com/one-piece-posters/#edward-weevil) |
| 75 | Hatchan | Six Sword Style Hachi | ฿&nbsp;8,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#hatchan) |
| 76 | Curly Dadan |  | ฿&nbsp;7,800,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#curly-dadan) |
| 77 | Shiryu | Shiryu of the Rain | ฿&nbsp;??? | Blackbeard Pirates | [poster](https://onepieceposter.com/one-piece-posters/#shiryu) |
| 78 | Vander Decken IX |  | ฿&nbsp;??? |  | [poster](https://onepieceposter.com/one-piece-posters/#vander-decken-ix) |
| 79 | Lucky Roux |  | ฿&nbsp;??? | Red Hair Pirates | [poster](https://onepieceposter.com/one-piece-posters/#lucky-roux) |
| 80 | Zeff | Red-Leg Zeff | ฿&nbsp;??? |  | [poster](https://onepieceposter.com/one-piece-posters/#zeff) |
| 81 | Belo Betty |  | ฿&nbsp;457,000,000 | Revolutionary Army | [poster](https://onepieceposter.com/one-piece-posters/#belo-betty) |
| 82 | Diamante |  | ฿&nbsp;99,000,000 | Donquixote Pirates | [poster](https://onepieceposter.com/one-piece-posters/#diamante) |
| 83 | Vista | Vista of the Flower Swords | ฿&nbsp;??? | Whitebeard Pirates | [poster](https://onepieceposter.com/one-piece-posters/#vista) |
| 84 | Dellinger |  | ฿&nbsp;15,000,000 | Donquixote Pirates | [poster](https://onepieceposter.com/one-piece-posters/#dellinger) |
| 85 | Who's-Who | Who of the Droplets | ฿&nbsp;546,000,000 | Beasts Pirates | [poster](https://onepieceposter.com/one-piece-posters/#whos-who) |
| 86 | Zala | Miss Doublefinger | ฿&nbsp;35,000,000 | Baroque Works | [poster](https://onepieceposter.com/one-piece-posters/#zala) |
| 87 | Charlotte Cracker | Thousand Arms Cracker | ฿&nbsp;860,000,000 | Big Mom Pirates | [poster](https://onepieceposter.com/one-piece-posters/#charlotte-cracker) |
| 88 | Urouge | Mad Monk | ฿&nbsp;108,000,000 | Worst Generation | [poster](https://onepieceposter.com/one-piece-posters/#urouge) |
| 89 | Brogy | Brogy the Red Ogre | ฿&nbsp;1,800,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#brogy) |
| 90 | Boa Sandersonia |  | ฿&nbsp;40,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#boa-sandersonia) |
| 91 | Dorry | Dorry the Blue Ogre | ฿&nbsp;1,800,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#dorry) |
| 92 | Kyros |  | ฿&nbsp;??? |  | [poster](https://onepieceposter.com/one-piece-posters/#kyros) |
| 93 | Trebol |  | ฿&nbsp;99,000,000 | Donquixote Pirates | [poster](https://onepieceposter.com/one-piece-posters/#trebol) |
| 94 | Capone Bege | Gang | ฿&nbsp;350,000,000 | Worst Generation | [poster](https://onepieceposter.com/one-piece-posters/#capone-bege) |
| 95 | Jesus Burgess | Champion | ฿&nbsp;20,000,000 | Blackbeard Pirates | [poster](https://onepieceposter.com/one-piece-posters/#jesus-burgess) |
| 96 | Scratchmen Apoo | Roar of the Sea | ฿&nbsp;350,000,000 | Worst Generation | [poster](https://onepieceposter.com/one-piece-posters/#scratchmen-apoo) |
| 97 | Sanjuan Wolf | Colossal Battleship | ฿&nbsp;??? | Blackbeard Pirates | [poster](https://onepieceposter.com/one-piece-posters/#sanjuan-wolf) |
| 98 | Pekoms |  | ฿&nbsp;330,000,000 | Big Mom Pirates | [poster](https://onepieceposter.com/one-piece-posters/#pekoms) |
| 99 | Nico Olvia |  | ฿&nbsp;79,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#nico-olvia) |
| 100 | Gin | Gin the Man-Demon | ฿&nbsp;12,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#gin) |
| 101 | Karasu |  | ฿&nbsp;400,000,000 | Revolutionary Army | [poster](https://onepieceposter.com/one-piece-posters/#karasu) |
| 102 | Laffitte | Demon Sheriff | ฿&nbsp;42,200,000 | Blackbeard Pirates | [poster](https://onepieceposter.com/one-piece-posters/#laffitte) |
| 103 | Pandaman |  | ฿&nbsp;3,333,333 |  | [poster](https://onepieceposter.com/one-piece-posters/#pandaman) |
| 104 | Vasco Shot | Heavy Drinker | ฿&nbsp;??? | Blackbeard Pirates | [poster](https://onepieceposter.com/one-piece-posters/#vasco-shot) |
| 105 | Charlotte Perospero |  | ฿&nbsp;700,000,000 | Big Mom Pirates | [poster](https://onepieceposter.com/one-piece-posters/#charlotte-perospero) |
| 106 | Lao G |  | ฿&nbsp;61,000,000 | Donquixote Pirates | [poster](https://onepieceposter.com/one-piece-posters/#lao-g) |
| 107 | Charlotte Daifuku |  | ฿&nbsp;300,000,000 | Big Mom Pirates | [poster](https://onepieceposter.com/one-piece-posters/#charlotte-daifuku) |
| 108 | Jozu | Diamond Jozu | ฿&nbsp;??? | Whitebeard Pirates | [poster](https://onepieceposter.com/one-piece-posters/#jozu) |
| 109 | Charlotte Amande | Demon Lady | ฿&nbsp;??? | Big Mom Pirates | [poster](https://onepieceposter.com/one-piece-posters/#charlotte-amande) |
| 110 | Gladius |  | ฿&nbsp;31,000,000 | Donquixote Pirates | [poster](https://onepieceposter.com/one-piece-posters/#gladius) |
| 111 | Sasaki | Overflowing Sasaki | ฿&nbsp;472,000,000 | Beasts Pirates | [poster](https://onepieceposter.com/one-piece-posters/#sasaki) |
| 112 | Yorki | Calico Yorki | ฿&nbsp;??? |  | [poster](https://onepieceposter.com/one-piece-posters/#yorki) |
| 113 | Page One |  | ฿&nbsp;290,000,000 | Beasts Pirates | [poster](https://onepieceposter.com/one-piece-posters/#page-one) |
| 114 | Avalo Pizarro | Corrupt King | ฿&nbsp;??? | Blackbeard Pirates | [poster](https://onepieceposter.com/one-piece-posters/#avalo-pizarro) |
| 115 | Bartolomeo | Bartolomeo the Cannibal | ฿&nbsp;200,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#bartolomeo) |
| 116 | Sai | Don Sai | ฿&nbsp;210,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#sai) |
| 117 | Little Oars Jr. |  | ฿&nbsp;550,000,000 | Whitebeard Pirates | [poster](https://onepieceposter.com/one-piece-posters/#little-oars-jr) |
| 118 | Bartholomew Kuma | Tyrant | ฿&nbsp;296,000,000 | Warlords | [poster](https://onepieceposter.com/one-piece-posters/#bartholomew-kuma) |
| 119 | Gill Bastar |  | ฿&nbsp;970,000,000 |  | [poster](https://onepieceposter.com/one-piece-posters/#gill-bastar) |
| 120 | Van Augur | The Supersonic | ฿&nbsp;64,000,000 | Blackbeard Pirates | [poster](https://onepieceposter.com/one-piece-posters/#van-augur) |

## Groups

| Key | English | Spanish | French | German | Portuguese (Brazil) | Italian | Indonesian |
|---|---|---|---|---|---|---|---|
| `straw-hats` | Straw Hats | Sombrero de Paja | Chapeau de paille | Strohhutbande | Chapéus de Palha | Cappello di paglia | Kru Topi Jerami |
| `emperors` | Emperors | Cuatro Emperadores | Empereurs | Kaiser | Imperadores | Imperatori | Yonko |
| `warlords` | Warlords | Señores de la Guerra del Mar | Grands Corsaires | Samurai der Meere | Shichibukai | Flotta dei sette | Shichibukai |
| `worst-generation` | Worst Generation | Peor Generación | Pire Génération | Schlimmste Generation | Pior Geração | Peggiore delle generazioni | Generasi Terburuk |
| `roger-pirates` | Roger Pirates | Piratas de Roger | Pirates de Roger | Roger-Piraten | Piratas do Roger | Pirati di Roger | Bajak Laut Roger |
| `red-hair-pirates` | Red Hair Pirates | Piratas del Pelirrojo | Équipage du Roux | Shanks’ Piraten | Piratas do Ruivo | Pirati del Rosso | Bajak Laut Rambut Merah |
| `whitebeard-pirates` | Whitebeard Pirates | Piratas de Barbablanca | Équipage de Barbe Blanche | Whitebeard-Piraten | Piratas do Barba Branca | Pirati di Barbabianca | Bajak Laut Shirohige |
| `beasts-pirates` | Beasts Pirates | Piratas de las Bestias | Équipage des Cent Bêtes | Hundert-Bestien-Piraten | Piratas Bestiais | Pirati delle cento bestie | Bajak Laut Beasts |
| `big-mom-pirates` | Big Mom Pirates | Piratas de Big Mom | Équipage de Big Mom | Big-Mum-Piraten | Piratas da Big Mom | Pirati di Big Mom | Bajak Laut Big Mom |
| `donquixote-pirates` | Donquixote Pirates | Piratas Donquixote | Équipage de Don Quijote | Donquixote-Piraten | Piratas Donquixote | Pirati di Donquijote | Bajak Laut Donquixote |
| `blackbeard-pirates` | Blackbeard Pirates | Piratas de Barbanegra | Équipage de Barbe Noire | Blackbeard-Piraten | Piratas do Barba Negra | Pirati di Barbanera | Bajak Laut Blackbeard |
| `baroque-works` | Baroque Works | Baroque Works | Baroque Works | Baroque-Firma | Baroque Works | Baroque Works | Baroque Works |
| `cross-guild` | Cross Guild | Cross Guild | Cross Guild | Cross Guild | Cross Guild | Cross Guild | Cross Guild |
| `revolutionaries` | Revolutionary Army | Ejército Revolucionario | Armée révolutionnaire | Revolutionsarmee | Exército Revolucionário | Armata rivoluzionaria | Pasukan Revolusioner |

## Wanted posters in every language

- English: https://onepieceposter.com/one-piece-posters/
- Spanish: https://onepieceposter.com/es/carteles-de-se-busca-one-piece/
- French: https://onepieceposter.com/fr/avis-de-recherche-one-piece/
- German: https://onepieceposter.com/de/one-piece-wanted-poster/
- Portuguese (Brazil): https://onepieceposter.com/pt/cartazes-de-procurado-one-piece/
- Italian: https://onepieceposter.com/it/poster-wanted-one-piece/
- Indonesian: https://onepieceposter.com/id/poster-wanted-one-piece/

## License and credit

The data is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). Please credit it with a link:

> One Piece Wanted Posters and Bounties by [onepieceposter.com](https://onepieceposter.com/one-piece-posters/), CC BY-SA 4.0

Local names and epithets were checked against the One Piece fan wikis at onepiece.fandom.com (Spanish, French, German, Portuguese, Italian and Indonesian), whose texts are licensed CC BY-SA.

ONE PIECE and its characters are the property of Eiichiro Oda, Shueisha and Toei Animation. This is an unofficial fan project and is not affiliated with them.

Found a wrong bounty or name? Please open an issue.

Updated 2026-10-26.
