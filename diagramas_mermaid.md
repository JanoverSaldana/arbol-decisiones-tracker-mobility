# Diagramas de Flujo - Visita Domiciliaria

## Flujo Principal

```mermaid
flowchart TD
    A[INICIO - Preparación] --> B{¿Documento válido?}
    B -->|NO| Z1[❌ RECHAZADO]
    B -->|SÍ| C{¿Reside en dirección?}
    C -->|NO| Z1
    C -->|SÍ| D{Tiempo permanencia}
    
    D -->|< 6 meses| Z1
    D -->|6-11 meses| E{¿Tiene contrato?}
    D -->|≥ 12 meses| F[+5 pts<br/>Permanencia]
    
    E -->|SÍ| F1[+3 pts<br/>Con contrato]
    E -->|NO| F2[-10 pts<br/>OBSERVADO ALTO]
    
    F --> G[Validación Arrendador]
    F1 --> G
    F2 --> G
    
    G --> H{¿Arrendador conoce?}
    H -->|No conoce/Suplanta| Z1
    H -->|Dudas significativas| I[-15 pts<br/>OBSERVADO ALTO]
    H -->|Confirma todo| J[+20 pts<br/>Validado]
    
    I --> K[Evaluación Vivienda]
    J --> K
    
    K --> L{Material + Techo + Estado}
    L -->|Noble+Tech+Bueno| M[+25 pts]
    L -->|NoNoble+NoTech+Malo| N[-10 pts<br/>OBSERVADO ALTO]
    L -->|Combinaciones medias| O[+5 a +20 pts]
    
    M --> P[Evaluación Cochera]
    N --> P
    O --> P
    
    P --> Q{¿Tiene cochera?}
    Q -->|Propia cerrada ≤4c| R[+15 pts]
    Q -->|En calle >4c| S[-3 pts<br/>OBSERVADO MEDIO]
    Q -->|Sin cochera| T[-8 pts<br/>OBSERVADO MEDIO]
    
    R --> U[Evaluación Zona]
    S --> U
    T --> U
    
    U --> V{¿Zona segura?}
    V -->|Peligrosa| Z1
    V -->|Segura+Fácil acceso| W[+10 pts]
    V -->|Cautelosa+Regular| X[-3 pts<br/>OBSERVADO MEDIO]
    
    W --> Y[Convivencia]
    X --> Y
    
    Y --> Z{¿Vive solo?}
    Z -->|SÍ| AA[-5 pts<br/>OBSERVADO MEDIO]
    Z -->|NO| BB[+0 pts]
    
    AA --> CC[CÁLCULO FINAL]
    BB --> CC
    
    CC --> DD{Puntuación Total}
    DD -->|≥ 70 pts| EE[✅ CONFORME]
    DD -->|50-69 pts| FF[⚠️ OBSERVADO]
    DD -->|< 50 pts| GG[❌ RECHAZADO]
    
    CC --> HH{Reglas de Eliminación}
    HH -->|2+ ALTOS| GG
    HH -->|1 ALTO + 2 MEDIOS| GG
    HH -->|4+ MEDIOS| GG
```

## Flujo de Puntuación

```mermaid
graph LR
    subgraph "IDENTIDAD Y RESID (30 pts)"
        A1[Documento válido: +15] 
        A2[Reside: +10]
        A3[Permanencia ≥12m: +5]
        A4[Permanencia 6-11m + contrato: +3]
        A5[Permanencia 6-11m sin contrato: -10]
    end
    
    subgraph "ARRENDADOR (20 pts)"
        B1[Confirma todo: +20]
        B2[Dudas menores: +10]
        B3[Inconsistencias: -5]
        B4[Dudas significativas: -15]
    end
    
    subgraph "VIVIENDA (25 pts)"
        C1[Noble+Tech+Bueno: +25]
        C2[Noble+Tech+Regular: +20]
        C3[NoNoble+Tech+Bueno: +15]
        C4[NoNoble+NoTech: -10]
        C5[Estado precario: -15]
    end
    
    subgraph "COCHERA (15 pts)"
        D1[Propia cerrada ≤4c: +15]
        D2[Alquilada cerrada ≤4c: +12]
        D3[En calle ≤4c: +5]
        D4[En calle >4c: -3]
        D5[Sin cochera: -8]
    end
    
    subgraph "ZONA (10 pts)"
        E1[Segura+Fácil+Vigilada: +10]
        E2[Cautelosa+Regular: +3]
        E3[No vigilada+Difícil: -3]
        E4[Inaccesible: -8]
    end
    
    subgraph "CONVIVENCIA" 
        F1[Vive acompañado: +0]
        F2[Vive solo: -5]
    end
    
    A1 --> TOTAL[PUNTUACIÓN TOTAL]
    A2 --> TOTAL
    A3 --> TOTAL
    A4 --> TOTAL
    A5 --> TOTAL
    B1 --> TOTAL
    B2 --> TOTAL
    B3 --> TOTAL
    B4 --> TOTAL
    C1 --> TOTAL
    C2 --> TOTAL
    C3 --> TOTAL
    C4 --> TOTAL
    C5 --> TOTAL
    D1 --> TOTAL
    D2 --> TOTAL
    D3 --> TOTAL
    D4 --> TOTAL
    D5 --> TOTAL
    E1 --> TOTAL
    E2 --> TOTAL
    E3 --> TOTAL
    E4 --> TOTAL
    F1 --> TOTAL
    F2 --> TOTAL
    
    TOTAL --> RESULTADO{Resultado Final}
    RESULTADO -->|≥ 70 pts| CONFORME[✅ CONFORME]
    RESULTADO -->|50-69 pts| OBSERVADO[⚠️ OBSERVADO]
    RESULTADO -->|< 50 pts| RECHAZADO[❌ RECHAZADO]
```

## Matriz de Decisión

```mermaid
graph TD
    subgraph "REGLAS ELIMINATORIAS"
        R1[Documento inválido] --> RECHAZO[❌ RECHAZO DIRECTO]
        R2[No reside] --> RECHAZO
        R3[< 6 meses] --> RECHAZO
        R4[Arrendador no conoce] --> RECHAZO
        R5[Zona peligrosa] --> RECHAZO
    end
    
    subgraph "OBSERVADOS ALTOS (-10 a -15 pts)"
        AH1[Sin contrato 6-11m: -10]
        AH2[Dudas arrendador: -15]
        AH3[Material+Techo malo: -10]
        AH4[Estado precario: -15]
        AH5[Acceso inaccesible: -8]
    end
    
    subgraph "OBSERVADOS MEDIOS (-3 a -8 pts)"
        AM1[Inconsistencias: -5]
        AM2[Cochera calle: -3]
        AM3[Cochera lejos: -3]
        AM4[Sin cochera: -8]
        AM5[Sin fotos: -5]
        AM6[Zona no vigilada: -3]
        AM7[Acceso regular: -3]
        AM8[Vive solo: -5]
    end
    
    AH1 --> CONTADOR_A[Contador ALTOS]
    AH2 --> CONTADOR_A
    AH3 --> CONTADOR_A
    AH4 --> CONTADOR_A
    AH5 --> CONTADOR_A
    
    AM1 --> CONTADOR_M[Contador MEDIOS]
    AM2 --> CONTADOR_M
    AM3 --> CONTADOR_M
    AM4 --> CONTADOR_M
    AM5 --> CONTADOR_M
    AM6 --> CONTADOR_M
    AM7 --> CONTADOR_M
    AM8 --> CONTADOR_M
    
    CONTADOR_A --> EVAL{Evaluación Combinada}
    CONTADOR_M --> EVAL
    
    EVAL -->|≥ 2 ALTOS| RECHAZO2[❌ RECHAZO POR ACUMULACIÓN]
    EVAL -->|1 ALTO + ≥2 MEDIOS| RECHAZO2
    EVAL -->|≥ 4 MEDIOS| RECHAZO2
    EVAL -->|Otros casos| PUNTUACION[Evaluación por Puntuación]
```

## Para generar estos diagramas visualmente:

### Opción 1: GitHub/GitLab
- Copia el código Mermaid en un archivo `.md`
- GitHub y GitLab renderizan automáticamente los diagramas Mermaid

### Opción 2: Herramientas Online
- **Mermaid Live Editor**: https://mermaid.live/
- **Draw.io**: Importa diagramas Mermaid
- **Lucidchart**: Soporta importación Mermaid

### Opción 3: VS Code
- Instala la extensión "Mermaid Preview"
- Visualiza los diagramas directamente en el editor

### Opción 4: Generar imágenes
```bash
# Usando mermaid-cli
npm install -g @mermaid-js/mermaid-cli
mmdc -i flujo_principal.mmd -o flujo_principal.png
```
