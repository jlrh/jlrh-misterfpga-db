# ROMs requeridas por core

> **Este repo NO distribuye ROMs.** Entrega únicamente los `.mra`. Cada usuario debe
> conseguir por su cuenta el set de ROMs que indica esta tabla y dejarlo en
> `/media/fat/games/mame/` (o `hbmame/`) de su MiSTer.

Todos los sets están fijados a **MAME 0.288** en variante **merged**: un único zip con el
nombre del **parent** que lleva dentro también los clones (los `.mra` lo declaran con
`type="merged"`). Las versiones alternativas de un juego (clones) usan ese mismo zip.
Verificado por CRC de cada ROM del `.mra` contra el set merged de MAME 0.288.

## Resumen

| Core (.mra) | zip esperado | MAME | merged | tipo 0.288 |
|---|---|---|:--:|---|
| Alligator Hunt (Gaelco, 1994) | `aligator.zip` | 0.288 | ✅ | parent |
| Big Karnak (Gaelco, 1991) | `bigkarnk.zip` | 0.288 | ✅ | parent |
| Biomechanical Toy (Gaelco, 1995) | `biomtoy.zip` | 0.288 | ✅ | parent |
| Destroyer (Cidelsa, 1980) | `destryer.zip` | 0.288 | ✅ | parent |
| Empire City 1931 (Seibu, 1986) | `empcity.zip` | 0.288 | ✅ | parent |
| Glass (Gaelco, 1993) | `glass.zip` | 0.288 | ✅ | clon `glassa` (dentro de `glass.zip`) |
| Guerrilla War (SNK, 1987, US) | `gwar.zip` | 0.288 | ✅ | parent |
| Mechanized Attack (SNK, 1989, World) | `mechatt.zip` + `ym2608.zip` | 0.288 | ✅ | parent (+ ROM interna del `ym2608`) |
| Operation Wolf (World, rev 2, set 1) | `opwolf.zip` + `cchip.zip` | 0.288 | ✅ | parent (+ dispositivo `cchip`) |
| Shadow Force (Technos, 1993, World v3) | `shadfrce.zip` | 0.288 | ✅ | parent |
| Shadow Force - Henshin Ninja (Technos, 1993, Japan v2) | `shadfrce.zip` | 0.288 | ✅ | clon `shadfrcej` (dentro de `shadfrce.zip`) |
| Shadow Force (Technos, 1993, US v2) | `shadfrce.zip` | 0.288 | ✅ | clon `shadfrceu` (dentro de `shadfrce.zip`) |
| Squash (Gaelco, 1992) | `squash.zip` | 0.288 | ✅ | parent |
| TH Strikes Back (Gaelco, 1994) | `thoop2.zip` | 0.288 | ✅ | parent |
| Thunder Hoop (Gaelco, 1992) | `thoop.zip` | 0.288 | ✅ | parent |
| World Rally 2 (Gaelco, 1995) | `wrally2.zip` | 0.288 | **⚠ pendiente** | parent |
| World Rally Championship (Gaelco, 1993, checksum 3873) | `wrally.zip` | 0.288 | ✅ | clon `wrallyc` (dentro de `wrally.zip`) |
| World Rally Championship (Gaelco, 1993, checksum DE0D) | `wrally.zip` | 0.288 | ✅ | parent |
| Xexex (ver EAA) (Konami, 1991) | `xexex.zip` | 0.288 | ✅ | parent |
| Orius (ver UAA) (Konami, 1991) | `xexex.zip` | 0.288 | ✅ | clon `orius` (dentro de `xexex.zip`) |
| Xexex (ver AAA) (Konami, 1991) | `xexex.zip` | 0.288 | ✅ | clon `xexexa` (dentro de `xexex.zip`) |
| Xexex (ver JAA) (Konami, 1991) | `xexex.zip` | 0.288 | ✅ | clon `xexexj` (dentro de `xexex.zip`) |

**Notas:**
- `best available` en `-verifyroms` = programa+gfx+sonido correctos; solo faltan **PLDs** (GAL/PAL, muchos sin dump), que el `.mra` no usa → equivale a set completo.
- **Glass** usa el clon `glassa`, que viene dentro del `glass.zip` merged; su programa `1.c23`/`2.c22` es distinto al del parent `glass` (`europa_c23…`).
- **World Rally** tiene dos revisiones, las dos en el mismo `wrally.zip` merged: `wrally` (parent, checksum DE0D, 4 faros) y `wrallyc` (clon, checksum 3873, 2 faros).
- **World Rally 2** ⚠ pendiente: el `.mra` espera un set no publicado como zip único (ver `HANDOFF`).
- **Operation Wolf** necesita además `cchip.zip`: la ROM interna del C-Chip (uPD78C11) es un romset de **dispositivo** aparte en MAME, no forma parte de `opwolf.zip`.
- **Shadow Force** tiene tres `.mra` con el mismo `shadfrce.zip`: la principal (versión mundial) y, en `_Arcade/_alternatives/_Shadow Force/`, la japonesa `Shadow Force - Henshin Ninja (FF, Technos, 1993, Japan v2)` y la americana `Shadow Force (FF, Technos, 1993, US v2)` (6 botones).
- **Xexex** tiene cuatro `.mra` con el mismo `xexex.zip`: la principal `Xexex (FF ver EAA)` y las alternativas `Orius (FF ver UAA)`, `Xexex (FF ver AAA)` y `Xexex (FF ver JAA)` en `_Arcade/_alternatives/_Xexex/`.

## Detalle por core (nombre + CRC de cada ROM del `.mra`)

### Alligator Hunt (Gaelco, 1994)

- **zip:** `aligator.zip` · **parent** · MAME 0.288 merged · set completo

| ROM | CRC | en zip |
|---|---|:--:|
| `1.u45` | `61c47c56` | OK |
| `2.u44` | `96bc77c2` | OK |
| `u48` | `19e03bf1` | OK |
| `u50` | `85daecf9` | OK |
| `u47` | `74a5a29f` | OK |
| `u49` | `70a4ee0b` | OK |
| `aligator_ds5002fp_sram.bin` | `6558f215` | OK |

### Big Karnak (Gaelco, 1991)

- **zip:** `bigkarnk.zip` · **parent** · MAME 0.288 merged · programa+gfx+sonido OK (faltan solo PLDs, no usados)

| ROM | CRC | en zip |
|---|---|:--:|
| `d16` | `44fb9c73` | OK |
| `d19` | `ff79dfdd` | OK |
| `h5` | `20e239ff` | OK |
| `h10` | `ab442855` | OK |
| `h8` | `83dce5a3` | OK |
| `h6` | `24e84b24` | OK |
| `d1` | `26444ad1` | OK |
| `d5` | `3b73b9c5` | OK |

### Biomechanical Toy (Gaelco, 1995)

- **zip:** `biomtoy.zip` · **parent** · MAME 0.288 merged · programa+gfx+sonido OK (faltan solo PLDs, no usados)

| ROM | CRC | en zip |
|---|---|:--:|
| `18.d18` | `4569ce64` | OK |
| `16.d16` | `739449bd` | OK |
| `j6` | `e923728b` | OK |
| `j7` | `0e18fac2` | OK |
| `j9` | `1c93f050` | OK |
| `j10` | `8e3e96cc` | OK |
| `h6` | `9416a729` | OK |
| `h7` | `9c984d7b` | OK |
| `h9` | `8c1f6718` | OK |
| `h10` | `aca1702b` | OK |
| `c1` | `0f02de7e` | OK |
| `c3` | `914e4bbc` | OK |

### Destroyer (Cidelsa, 1980)

- **zip:** `destryer.zip` · **parent** · MAME 0.288 merged · set completo

| ROM | CRC | en zip |
|---|---|:--:|
| `des a 2.ic4` | `63749870` | OK |
| `des b 2.ic5` | `60604f40` | OK |
| `des c 2.ic6` | `a7cdeb7b` | OK |
| `des d 2.ic7` | `dbec0aea` | OK |

### Empire City 1931 (Seibu, 1986)

- **zip:** `empcity.zip` · **parent** · MAME 0.288 merged · set completo

| ROM | CRC | en zip |
|---|---|:--:|
| `ec_01.rom` | `fe01d9b1` | OK |
| `ec_02.rom` | `b3cf1ef7` | OK |
| `ec_04.rom` | `aa3e7d1e` | OK |
| `5j` | `1b8d0c07` | OK |
| `9.7c` | `8ceaf4fe` | OK |
| `10.8c` | `5a1a227a` | OK |
| `15.7j` | `27a310bc` | OK |
| `16.8j` | `3d19ce18` | OK |
| `5.2c` | `0c099a31` | OK |
| `6.3c` | `3cc77c31` | OK |
| `7.4c` | `2c6caa5f` | OK |
| `8.5c` | `e11ded31` | OK |
| `11.2j` | `8261ecfe` | OK |
| `12.3j` | `71137301` | OK |
| `13.4c` | `0ae48dd3` | OK |
| `14.5j` | `debf5d76` | OK |
| `18.6w` | `68acd627` | OK |
| `19.7w` | `5170a057` | OK |
| `20.8w` | `8299f247` | OK |
| `21.9w` | `b57dc037` | OK |
| `empcityu_68705.3j` | `182f7616` | OK |
| `17.2n` | `1b3706b5` | OK |
| `82s129.006` | `f9424b5b` | OK |
| `82s129.002` | `c883d49b` | OK |
| `82s129.003` | `af81882a` | OK |
| `82s129.004` | `1831ce7c` | OK |
| `82s129.005` | `96cb6293` | OK |
| `82s129.052` | `3d915ffc` | OK |
| `82s129.066` | `51e8832f` | OK |

### Glass (Gaelco, 1993)

- **zip:** `glass.zip` · **clon `glassa`** · MAME 0.288 merged · set completo

| ROM | CRC | en zip |
|---|---|:--:|
| `1.c23` | `aeebd4ed` | OK |
| `2.c22` | `165e2e01` | OK |
| `h13.bin` | `13ab7f31` | OK |
| `h11.bin` | `c6ac41c8` | OK |
| `c1.bin` | `d9f075a2` | OK |
| `h9.bin` | `b9492557` | OK |
| `glass_ds5002fp_sram.bin` | `47c9df4c` | OK |

### Operation Wolf (World, rev 2, set 1)

- **zip:** `opwolf.zip` + `cchip.zip` (dispositivo) · **parent** · MAME 0.288 merged · set completo

| ROM | CRC | en zip |
|---|---|:--:|
| `b20-05-02.40` | `3ffbfe3a` | OK |
| `b20-03-02.30` | `fdabd8a5` | OK |
| `b20-04.39` | `216b4838` | OK |
| `b20-20.29` | `d244431a` | OK |
| `b20-07.10` | `45c7ace3` | OK |
| `b20-08.21` | `f3e19c64` | OK |
| `b20-13.13` | `f6acdab1` | OK |
| `b20-14.72` | `89f889e5` | OK |
| `cchip_upd78c11.bin` | `43021521` | OK |
| `b20-18.73` | `5987b4e9` | OK |

### Squash (Gaelco, 1992)

- **zip:** `squash.zip` · **parent** · MAME 0.288 merged · set completo

| ROM | CRC | en zip |
|---|---|:--:|
| `squash.d18` | `ce7aae96` | OK |
| `squash.d16` | `8ffaedd7` | OK |
| `squash.c12` | `5c440645` | OK |
| `squash.c11` | `9e19694d` | OK |
| `squash.c10` | `892a035c` | OK |
| `squash.c09` | `0bb91c69` | OK |
| `squash.d01` | `a1b9651b` | OK |

### TH Strikes Back (Gaelco, 1994)

- **zip:** `thoop2.zip` · **parent** · MAME 0.288 merged · set completo

| ROM | CRC | en zip |
|---|---|:--:|
| `3.c23` | `6cd4a8dc` | OK |
| `2.c22` | `59ba9b43` | OK |
| `th2-h8.h8` | `60328a11` | OK |
| `th2-h12.h12` | `b25c2d3e` | OK |
| `th2-c1.c1` | `8fac8c30` | OK |
| `thoop2_ds5002fp.bin` | `6881384d` | OK |

### Thunder Hoop (Gaelco, 1992)

- **zip:** `thoop.zip` · **parent** · MAME 0.288 merged · set completo

| ROM | CRC | en zip |
|---|---|:--:|
| `th18dea1.040` | `59bad625` | OK |
| `th161eb4.020` | `6add61ed` | OK |
| `th18dea1.040` | `59bad625` | OK |
| `th161eb4.020` | `6add61ed` | OK |
| `c12` | `29a5ca36` | OK |
| `c11` | `7403ef7e` | OK |
| `c10` | `2d227085` | OK |
| `c09` | `06f0edbf` | OK |
| `sound` | `99f80961` | OK |

### World Rally 2 (Gaelco, 1995)

- **zip:** `wrally2.zip` · **parent** · MAME 0.288 merged · ⚠ pendiente

| ROM | CRC | en zip |
|---|---|:--:|
| `wr2_64.ic64` | `4cdf4e1e` | FALTA |
| `wr2_63.ic63` | `94887c9f` | FALTA |
| `wrally2_ds5002fp_sram.bin` | `4c532e9e` | FALTA |

### World Rally Championship (Gaelco, 1993, checksum 3873)

- **zip:** `wrally.zip` · **clon `wrallyc`** · MAME 0.288 merged · programa+gfx+sonido OK (faltan solo PLDs, no usados)

| ROM | CRC | en zip |
|---|---|:--:|
| `c22.bin` | `56da43b6` | OK |
| `c23.bin` | `8b7d93c3` | OK |
| `worldr18.i07` | `b37c807e` | OK |
| `worldr19.i09` | `018b35bb` | OK |
| `worldr20.i11` | `58b2809a` | OK |
| `worldr21.i13` | `b7fddb12` | OK |
| `worldr14.c01` | `e931c2ee` | OK |
| `worldr15.c03` | `11f0fe2c` | OK |
| `wrdallas.bin` | `547d1768` | OK |

### World Rally Championship (Gaelco, 1993, checksum DE0D)

- **zip:** `wrally.zip` · **parent** · MAME 0.288 merged · programa+gfx+sonido OK (faltan solo PLDs, no usados)

| ROM | CRC | en zip |
|---|---|:--:|
| `invers_taula_c22_coche_8-11-93_o.bin` | `af91579b` | OK |
| `invers_taula_c23_coche_8-11-93_e.bin` | `593189bf` | OK |
| `worldr18.i07` | `b37c807e` | OK |
| `worldr19.i09` | `018b35bb` | OK |
| `worldr20.i11` | `58b2809a` | OK |
| `worldr21.i13` | `b7fddb12` | OK |
| `worldr14.c01` | `e931c2ee` | OK |
| `worldr15.c03` | `11f0fe2c` | OK |
| `wrdallas.bin` | `547d1768` | OK |

### Xexex (ver EAA) (Konami, 1991)

- **zip:** `xexex.zip` · **parent** (set `xexex`) · MAME 0.288 merged · set completo

| ROM | CRC | en zip |
|---|---|:--:|
| `067eaa02.16f` | `36ea7a48` | OK |
| `067eaa01.16d` | `3ebcb066` | OK |
| `067b04.13f` | `26ec5dc8` | OK |
| `067b03.13d` | `97833086` | OK |
| `067eaa05.4e` | `0e33d6ec` | OK |
| `067b06.3e` | `3b12fce4` | OK |
| `067b07.1e` | `ec87fe1b` | OK |
| `067b08.22f` | `ca816b7b` | OK |
| `067b14.1n` | `02a44bfa` | OK |
| `067b13.2n` | `633c8eb5` | OK |
| `067b12.17n` | `08d611b0` | OK |
| `067b11.19n` | `a26f7507` | OK |
| `067b10.20n` | `ee31db8d` | OK |
| `067b09.22n` | `88f072ef` | OK |

### Orius (ver UAA) (Konami, 1991)

- **zip:** `xexex.zip` · **clon de `xexex`** (set `orius`) · MAME 0.288 merged · set completo

| ROM | CRC | en zip |
|---|---|:--:|
| `067uaa02.16f` | `77709f64` | OK |
| `067uaa01.16d` | `f1263d3e` | OK |
| `067b04.13f` | `26ec5dc8` | OK |
| `067b03.13d` | `97833086` | OK |
| `067uaa05.4e` | `0e33d6ec` | OK |
| `067b06.3e` | `3b12fce4` | OK |
| `067b07.1e` | `ec87fe1b` | OK |
| `067b08.22f` | `ca816b7b` | OK |
| `067b14.1n` | `02a44bfa` | OK |
| `067b13.2n` | `633c8eb5` | OK |
| `067b12.17n` | `08d611b0` | OK |
| `067b11.19n` | `a26f7507` | OK |
| `067b10.20n` | `ee31db8d` | OK |
| `067b09.22n` | `88f072ef` | OK |

### Xexex (ver AAA) (Konami, 1991)

- **zip:** `xexex.zip` · **clon de `xexex`** (set `xexexa`) · MAME 0.288 merged · set completo

| ROM | CRC | en zip |
|---|---|:--:|
| `067aaa02.16f` | `b7b98d52` | OK |
| `067aaa01.16d` | `cf557144` | OK |
| `067b04.13f` | `26ec5dc8` | OK |
| `067b03.13d` | `97833086` | OK |
| `067eaa05.4e` | `0e33d6ec` | OK |
| `067b06.3e` | `3b12fce4` | OK |
| `067b07.1e` | `ec87fe1b` | OK |
| `067b08.22f` | `ca816b7b` | OK |
| `067b14.1n` | `02a44bfa` | OK |
| `067b13.2n` | `633c8eb5` | OK |
| `067b12.17n` | `08d611b0` | OK |
| `067b11.19n` | `a26f7507` | OK |
| `067b10.20n` | `ee31db8d` | OK |
| `067b09.22n` | `88f072ef` | OK |

### Xexex (ver JAA) (Konami, 1991)

- **zip:** `xexex.zip` · **clon de `xexex`** (set `xexexj`) · MAME 0.288 merged · set completo

| ROM | CRC | en zip |
|---|---|:--:|
| `067jaa02.16f` | `30ae5bc4` | OK |
| `067jaa01.16d` | `06e99784` | OK |
| `067b04.13f` | `26ec5dc8` | OK |
| `067b03.13d` | `97833086` | OK |
| `067jaa05.4e` | `2f4dd0a8` | OK |
| `067b06.3e` | `3b12fce4` | OK |
| `067b07.1e` | `ec87fe1b` | OK |
| `067b08.22f` | `ca816b7b` | OK |
| `067b14.1n` | `02a44bfa` | OK |
| `067b13.2n` | `633c8eb5` | OK |
| `067b12.17n` | `08d611b0` | OK |
| `067b11.19n` | `a26f7507` | OK |
| `067b10.20n` | `ee31db8d` | OK |
| `067b09.22n` | `88f072ef` | OK |
