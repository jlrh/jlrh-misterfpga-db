# jlrh — Arcade cores para MiSTer (base de datos unificada)

Base de datos única para el **MiSTer Downloader / Update All** con **todos** los
cores arcade portados a MiSTer (FPGA) por [**jlrh**](https://github.com/jlrh):
Gaelco, Taito (Seibu) y las familias que se vayan publicando. Al añadir esta
base de datos, tus `.rbf` y `.mra` se instalan y **actualizan solos** desde el
menú *Scripts*.

> ⚠️ **Solo cores + MRA. Aquí NO hay ROMs.** Los `.mra` son recetas; tú aportas
> tus propias ROMs (colócalas en `games/mame/`). Sin las ROMs correctas el core
> no arranca.

> ℹ️ **Un único db por plataforma.** Este repo sustituye a los antiguos db por
> familia (`gaelco-fpga-db`, …). Si ya tenías uno de esos, cambia su `db_url` por
> el de aquí — el Downloader deduplica por hash, así que no vuelves a descargar
> nada.

---

## Cómo instalarlo en tu MiSTer

Tienes dos opciones. Con **cualquiera** de las dos, la próxima vez que ejecutes
`update` o `update_all` desde el menú *Scripts* se descargarán los cores.

### Opción A — Update All (recomendada)

1. Abre `Scripts → update_all`.
2. Entra en **Databases** y añade la URL de esta base de datos:
   ```
   https://raw.githubusercontent.com/jlrh/jlrh-misterfpga-db/db/db.json.zip
   ```
3. Guarda y ejecuta. Update All sincroniza estos cores junto al resto.

### Opción B — Downloader (manual)

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
| Destroyer (Cidelsa, 1980) | 1980 | cidelsa | `destroyer_20260702` | Destroyer (Cidelsa, 1980).mra |
| Empire City 1931 (Seibu, 1986) | 1986 | seibu | `empirecity_20260718` | Empire City 1931 (Seibu, 1986).mra |
| Big Karnak (Gaelco, 1991) | 1991 | gaelco | `bigkarnk_20260701` | Big Karnak (Gaelco, 1991).mra |
| Squash (Gaelco, 1992) | 1992 | gaelco | `squash_20260714` | Squash (Gaelco, 1992).mra |
| Thunder Hoop (Gaelco, 1992) | 1992 | gaelco | `thoop_20260714` | Thunder Hoop (Gaelco, 1992).mra |
| Glass (Gaelco, 1993) | 1993 | gaelco | `glass_20260713` | Glass (Gaelco, 1993).mra |
| World Rally Championship (Gaelco, 1993) | 1993 | gaelco | `wrally_20260701` | World Rally Championship (Gaelco, 1993).mra |
| Alligator Hunt (Gaelco, 1994) | 1994 | gaelco | `aligator_20260714` | Alligator Hunt (Gaelco, 1994).mra |
| TH Strikes Back (Gaelco, 1994) | 1994 | gaelco | `thoop2_20260714` | TH Strikes Back (Gaelco, 1994).mra |
| Biomechanical Toy (Gaelco, 1995) | 1995 | gaelco | `biomtoy_20260714` | Biomechanical Toy (Gaelco, 1995).mra |
| World Rally 2 (Gaelco, 1995) | 1995 | gaelco | `wrally2_20260701` | World Rally 2 (Gaelco, 1995).mra |
| Operation Wolf (World, rev 2, set 1) |  | taito | `opwolf_20260718` | Operation Wolf (World, rev 2, set 1).mra |

<!-- CORES:AUTO:END -->

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
