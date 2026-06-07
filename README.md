[readme.md](https://github.com/user-attachments/files/28677056/readme.md)
# Calculadora de Rotlles d'Acer

Aplicació web progressiva (PWA) per calcular la longitud i el pes de cintes d'acer en rotlle destinades a la fabricació de tubs per conformació longitudinal i soldadura làser.

## Característiques

- Càlcul de metres de cinta a partir de les dimensions del rotlle
- Càlcul de metres de tub després de l'estirat (reducció de diàmetre)
- Càlcul del pes en funció del material (Acer 304 o 316L)
- Dos modes d'entrada per al rotlle: **Ø exterior / Ø interior** o **Corona / Ø interior**
- Possibilitat d'afegir múltiples cintes amb els mateixos paràmetres d'un sol cop
- Registre acumulat de totes les cintes introduïdes amb totals
- Eliminació individual de cintes per corregir errors
- Disseny adaptat a mòbil (responsive)
- Instal·lable com a app al mòbil (PWA) amb suport offline

## Fórmules utilitzades

**Longitud de cinta del rotlle:**
```
L = 0,7854 × (Øext² − Øint²) / (espessor × 1000)
```

**Longitud de tub després de l'estirat** (conservació de volum, espessor constant):
```
L_tub = L_cinta × (Ø_tub_inicial + espessor/2) / Ø_tub_final
```
on `Ø_tub_inicial = ample_cinta / π`

**Pes de la cinta:**
```
Pes (kg) = L_cinta × (ample / 1000) × (espessor / 1000) × densitat
```
- Acer 304 → 7.900 kg/m³
- Acer 316L → 7.980 kg/m³

## Estructura del projecte

```
├── index.html       # Aplicació principal
├── manifest.json    # Manifest PWA
├── sw.js            # Service Worker (funcionament offline)
├── icon-192.png     # Icona app (192×192 px)
├── icon-512.png     # Icona app (512×512 px)
└── README.md
```

## Instal·lació i ús

### Allotjament a GitHub Pages

1. Crea un repositori nou a GitHub
2. Puja tots els fitxers del projecte
3. Ves a **Settings → Pages** i selecciona la branca `main` com a origen
4. GitHub generarà una URL del tipus `https://usuari.github.io/nom-repositori`

> ⚠️ **Important:** edita el camp `"start_url"` del fitxer `manifest.json` perquè coincideixi amb la ruta del teu repositori. Per exemple, si el repositori es diu `rotlles-acer`, canvia `"start_url": "/"` per `"start_url": "/rotlles-acer/"`.

### Icones

El repositori conté una icona en dues mides diferente:
- `icon-192.png` (192×192 px)
- `icon-512.png` (512×512 px)

En cas de voler canviar-les, pots generar-les fàcilment a [favicon.io](https://favicon.io) o [realfavicongenerator.net](https://realfavicongenerator.net).

### Instal·lació al mòbil

**Android (Chrome):**
Obre la URL a Chrome → toca el menú ⋮ → *Afegeix a la pantalla d'inici*

**iPhone/iPad (Safari):**
Obre la URL a Safari → toca el botó de compartir ↑ → *Afegeix a la pantalla d'inici*

Un cop instal·lada, l'app funciona completament sense connexió a internet.

## Requisits tècnics

No requereix cap servidor ni instal·lació de dependències. Tot el codi és HTML, CSS i JavaScript estàtic. Les icones de la interfície es carreguen des de la CDN de [Tabler Icons](https://tabler-icons.io).

## Llicència

Ús intern. Tots els drets reservats.
