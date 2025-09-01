# Árbol de Decisiones - Visita Domiciliaria (Representación Visual)

```
                                    INICIO
                                      |
                               [PREPARACIÓN]
                                      |
                              ¿Documento válido?
                                   /     \
                                 NO       SÍ
                                 |         |
                            [RECHAZADO]    ¿Reside en dirección?
                                              /            \
                                           NO               SÍ
                                           |                |
                                    [RECHAZADO]      ¿Tiempo permanencia?
                                                      /        |        \
                                                  <6 meses   6-11m    ≥12m
                                                     |         |        |
                                                [RECHAZADO]    |    [+5 pts]
                                                               |
                                                     ¿Tiene contrato?
                                                        /        \
                                                      SÍ         NO
                                                      |          |
                                                  [+3 pts]  [-10 pts]
                                                      |          |
                                                       \        /
                                                    VALIDACIÓN ARRENDADOR
                                                           |
                                                  ¿Arrendador conoce?
                                                    /      |      \
                                               No conoce  Dudas   Confirma
                                                  |        |        |
                                            [RECHAZADO] [-15 pts] [+20 pts]
                                                         |         |
                                                          \       /
                                                        EVALUACIÓN VIVIENDA
                                                              |
                                                    ┌─────────┼─────────┐
                                                    |         |         |
                                              Material    Techo     Estado
                                              /    \      /   \     /    \
                                           Noble  NoNoble Tech NoTech Bueno Malo
                                            |       |      |     |     |     |
                                        [+15]   [-5]   [+10] [-5]  [+5]  [-10]
                                             \      |      |   /      |    /
                                              \     |      |  /       |   /
                                               ─────┼──────┼─────────┼──
                                                    |      |         |
                                                 SUMA PUNTOS VIVIENDA
                                                         |
                                                  EVALUACIÓN COCHERA
                                                         |
                                                ¿Tiene cochera?
                                                   /        \
                                                 SÍ          NO
                                                 |           |
                                           ¿Condiciones?  [-8 pts]
                                           /    |    \       |
                                      Óptima  Calle  Lejos   |
                                        |      |      |      |
                                    [+15]   [-3]   [-3]     |
                                         \     |     /      /
                                          \    |    /      /
                                           ─────┼────────
                                                |
                                         EVALUACIÓN ZONA
                                                |
                                        ¿Zona segura?
                                       /      |      \
                                   Segura  Cautela  Peligrosa
                                     |       |         |
                                  [+10]   [+5]    [RECHAZADO]
                                     |       |
                                      \     /
                                    ¿Acceso fácil?
                                      /      \
                                   Fácil    Difícil
                                     |        |
                                  [+5]     [-8]
                                     |        |
                                      \      /
                                   CONVIVENCIA
                                       |
                                 ¿Vive solo?
                                   /      \
                                 SÍ        NO
                                 |         |
                              [-5]      [+0]
                                 |         |
                                  \       /
                               CÁLCULO FINAL
                                     |
                            ┌────────┼────────┐
                            |        |        |
                       ≥70 pts   50-69 pts  <50 pts
                            |        |        |
                      [CONFORME] [OBSERVADO] [RECHAZADO]
                            |        |        |
                        Aprobado  Evidencias  Denegado
```

## Leyenda de Símbolos

- `[ ]` = Resultado/Puntuación
- `¿ ?` = Pregunta de decisión
- `→` = Flujo directo
- `|, /, \, ─` = Conexiones del árbol
- `[RECHAZADO]` = Eliminatorio inmediato
- `[+X pts]` = Suma puntos
- `[-X pts]` = Resta puntos/penalización

## Flujo de Eliminación Temprana

```
DOCUMENTO INVÁLIDO → RECHAZO INMEDIATO
NO RESIDE → RECHAZO INMEDIATO  
< 6 MESES → RECHAZO INMEDIATO
ARRENDADOR NO CONOCE → RECHAZO INMEDIATO
ZONA PELIGROSA → RECHAZO INMEDIATO
```

## Matriz de Combinaciones Críticas

```
OBSERVADOS ALTOS (≥2) → RECHAZO AUTOMÁTICO
├── Sin contrato 6-11m (-10)
├── Dudas arrendador (-15)  
├── Material no noble + no techada (-10)
├── Estado precario (-15)
└── Acceso inaccesible (-8)

OBSERVADOS MEDIOS (≥4) → RECHAZO AUTOMÁTICO
├── Inconsistencias arrendador (-5)
├── Cochera en calle (-3)
├── Cochera >4 cuadras (-3)
├── Sin cochera (-8)
├── Negativa fotos (-5)
├── Zona no vigilada (-3)
├── Acceso regular (-3)
└── Vive solo (-5)

1 ALTO + 2 MEDIOS → RECHAZO AUTOMÁTICO
```

## Rutas Típicas de Aprobación

### Ruta Óptima (90-100 pts)
```
Documento válido → Reside → >12 meses → Arrendador confirma 
→ Vivienda noble/techada/buena → Cochera propia cerrada 
→ Zona segura/acceso fácil → Vive acompañado
= 95 puntos = CONFORME
```

### Ruta Aceptable (70-85 pts)
```
Documento válido → Reside → 6-11m con contrato → Arrendador confirma
→ Vivienda no noble pero techada/regular → Cochera alquilada 
→ Zona cautelosa/acceso regular → Vive solo
= 75 puntos = CONFORME
```

### Ruta Observada (50-69 pts)
```
Documento válido → Reside → 6-11m sin contrato → Arrendador dudas menores
→ Vivienda no noble/techada/regular → Sin cochera → Zona cautelosa
= 55 puntos = OBSERVADO (solicitar contrato + plan cochera)
```
