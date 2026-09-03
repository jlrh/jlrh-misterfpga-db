# jlrh — Arcade cores para MiSTer (base de datos unificada)

Base de datos única para el **MiSTer Downloader** con **todos** los
cores arcade portados a MiSTer (FPGA) por [**jlrh**](https://github.com/jlrh):
Gaelco, Taito (Seibu) y las familias que se vayan publicando. Al añadir esta
base de datos, tus `.rbf` y `.mra` se instalan y **actualizan solos** desde el
menú *Scripts*.

> ⚠️ **Solo cores + MRA. Aquí NO hay ROMs.** Los `.mra` son recetas; tú aportas
> tus propias ROMs (colócalas en `games/mame/`). Sin las ROMs correctas el core
> no arranca. 👉 **[`ROMS.md`](ROMS.md)** indica el set exacto que espera cada
> core (nombre de zip, variante **non-merged**, versión **MAME 0.288** y CRC de cada ROM).

> ℹ️ **Un único db por plataforma.** Este repo sustituye a los antiguos db por
> familia (`gaelco-fpga-db`, …). Si ya tenías uno de esos, cambia su `db_url` por
> el de aquí — el Downloader deduplica por hash, así que no vuelves a descargar
> nada.

---

## Cómo instalarlo en tu MiSTer

Añade esta sección a tu `downloader.ini` (en la raíz de la SD):

```ini
[jlrh/jlrh-misterfpga-db]
db_url = https://raw.githubusercontent.com/jlrh/jlrh-misterfpga-db/db/db.json.zip
```

Luego ejecuta `Scripts → update`.

---

## Cores incluidos

Todos validados en hardware real (MiSTer). Nomenclatura estándar
`corename_YYYYMMDD.rbf`. **Esta tabla se genera automáticamente** desde los repos
de familia (`<familia>-fpga`): un core aparece aquí **si y solo si** tiene release
publicada. No se edita a mano.

<!-- CORES:AUTO:START -->

| Juego | Año | Familia | Core (`.rbf`) | MRA |
|-------|-----|---------|---------------|-----|
| Destroyer (FF, Cidelsa, 1980) | 1980 | cidelsa | `destroyer_20260702` | Destroyer (FF, Cidelsa, 1980).mra |
| Empire City 1931 (FF, Seibu, 1986) | 1986 | seibu | `empirecity_20260718` | Empire City 1931 (FF, Seibu, 1986).mra |
| Big Karnak (FF, Gaelco, 1991) | 1991 | gaelco | `bigkarnk_20260901` | Big Karnak (FF, Gaelco, 1991).mra |
| Squash (FF, Gaelco, 1992) | 1992 | gaelco | `squash_20260901` | Squash (FF, Gaelco, 1992).mra |
| Thunder Hoop (FF, Gaelco, 1992) | 1992 | gaelco | `thoop_20260901` | Thunder Hoop (FF, Gaelco, 1992).mra |
| Wild West C.O.W.-Boys of Moo Mesa (FF, Konami, 1992) | 1992 | konami | `moomesa_20260728` | Wild West C.O.W.-Boys of Moo Mesa (FF, Konami, 1992).mra |
| Glass (FF, Gaelco, 1993) | 1993 | gaelco | `glass_20260713` | Glass (FF, Gaelco, 1993).mra |
| Martial Champion (FF ver EAB) | 1993 | konami | `mtlchamp_20260903` | Martial Champion (FF ver EAB).mra |
| Alligator Hunt (FF, Gaelco, 1994) | 1994 | gaelco | `aligator_20260714` | Alligator Hunt (FF, Gaelco, 1994).mra |
| TH Strikes Back (FF, Gaelco, 1994) | 1994 | gaelco | `thoop2_20260714` | TH Strikes Back (FF, Gaelco, 1994).mra |
| Biomechanical Toy (FF, Gaelco, 1995) | 1995 | gaelco | `biomtoy_20260901` | Biomechanical Toy (FF, Gaelco, 1995).mra |
| World Rally 2 (FF, Gaelco, 1995) | 1995 | gaelco | `wrally2_20260701` | World Rally 2 (FF, Gaelco, 1995).mra |
| Asterix (FF ver EAD) |  | konami | `asterix_20260730` | Asterix (FF ver EAD).mra |
| Mystic Warriors (FF ver EAA) |  |  | `mystwarr_20260903` | Mystic Warriors (FF ver EAA).mra |
| Operation Wolf (FF, World, rev 2, set 1) |  | taito | `opwolf_20260718` | Operation Wolf (FF, World, rev 2, set 1).mra |
| Sunset Riders (FF 2 Players ver EBD) |  | konami | `ssriders_20260831` | Sunset Riders (FF 2 Players ver EBD).mra |
| Sunset Riders (FF 4 Players ver EAC) |  | konami | `ssriders_20260831` | Sunset Riders (FF 4 Players ver EAC).mra |
| World Rally Championship (FF, Gaelco, 1993, checksum 3873) |  | gaelco | `wrally_20260701` | World Rally Championship (FF, Gaelco, 1993, checksum 3873).mra |
| World Rally Championship (FF, Gaelco, 1993, checksum DE0D) |  | gaelco | `wrally_20260701` | World Rally Championship (FF, Gaelco, 1993, checksum DE0D).mra |

<!-- CORES:AUTO:END -->

> **World Rally Championship** viene en **dos variantes**, que se distinguen por el *checksum* que el
> juego muestra al arrancar. Ambas usan el **mismo `.rbf`**; solo cambia la ROM:
> - **checksum DE0D** — coche con **4 faros** en la presentación (set `wrally` → **`wrally.zip`**).
> - **checksum 3873** — coche con **2 faros** (set `wrallyc` → **`wrallyc.zip`**).
>
> Necesitas el `.zip` correspondiente a la variante que quieras (romset **MAME 0.288 non-merged**).

---

## Estructura del repositorio

La estructura de carpetas se replica **idéntica** en la SD del MiSTer:

```
_Arcade/
├── *.mra              → _Arcade/ en la SD
└── cores/
    └── *.rbf          → _Arcade/cores/ en la SD
```

La base de datos (`db/db.json.zip`) la genera **GitHub Actions** en cada push
(ver la pestaña *Actions*). No hay que construirla a mano. El contenido de
`_Arcade/` lo produce el generador `build_misterfpga_db.py` a partir de los
repos de familia — nunca se toca a mano.

---

## Créditos y licencia

Cores construidos sobre **[JTFRAME](https://github.com/jotego/jtframe)** de
**Jose Tejada (jotego)**. Publicados bajo **GPL-3.0** (ver `LICENSE`). El prefijo
`jt` se reserva para los cores oficiales de jotego; estos usan `corename` sin `jt`.

Base de datos generada con la
[plantilla DB de theypsilon](https://github.com/theypsilon/DB-Template_MiSTer).
