# IREC — Índice de Recuperación Económica de Caldas

Herramienta de seguimiento mensual de la actividad económica para acompañar la estrategia **Reconstruir es Avanzar**, de la **Gobernación de Caldas**. La identidad visual corresponde a la imagen suministrada al proyecto.

El IREC resume una batería de indicadores de industria, construcción, agroindustria y comercio exterior. Se publica **un único índice: el compuesto geométrico con pesos iguales por bloque**. El factor dinámico se conserva como herramienta interna de contraste y pronóstico. La regla de publicación se mantiene independientemente de que la variación sea positiva o negativa. La palabra recuperación identifica el propósito de seguimiento de la estrategia; no significa que se haya identificado un efecto causal del terremoto ni que se esté publicando PIB mensual.

## Contenido y publicación

Este paquete contiene únicamente `index.html` y este `README.md`. El HTML incorpora el logo, los datos, estilos, gráficos SVG e interacciones. No utiliza CDN, fuentes remotas, API, servicios de terceros ni bibliotecas externas durante su ejecución. Los enlaces de fuentes se abren solamente cuando el lector los consulta.

Para GitHub Pages, cargar **el contenido de esta carpeta** a la raíz del repositorio de publicación. En Settings → Pages, elegir **Deploy from a branch**, la rama de publicación y **/(root)**. El archivo de entrada es `index.html`, en minúsculas. No se requiere instalar dependencias ni compilar el sitio. Si se conserva la carpeta `git/` dentro de otro repositorio, se requiere un flujo de publicación que copie su contenido a la raíz del artefacto; GitHub Pages no ofrece `git/` como carpeta de origen en la configuración simple de rama. [Documentación oficial de GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site).

También puede abrirse `index.html` directamente sin conexión. JavaScript debe estar habilitado. El interruptor **Mostrar proyección** está apagado inicialmente y controla la línea proyectada, su banda, tabla y explicación. La estimación inicial de julio se conserva visible aunque la proyección esté apagada. El selector principal permite ver 3 o 6 meses, el último año, los últimos 2 años o toda la historia. Los periodos se cuentan hasta el último mes con información, incluida la estimación inicial; el horizonte de proyección se muestra a continuación. La comparación observado–estimado se conserva en la documentación técnica y los resultados internos. En el gráfico principal, las flechas del teclado permiten consultar cada mes. Los botones de información muestran fuentes, unidades, definiciones y método. La línea del sismo aparece en todos los gráficos con eje temporal. El recorrido público presenta el resumen del IREC, la disponibilidad del mes parcial, la evolución temporal y los aportes y movimientos de sus componentes. La proyección es opcional y permanece apagada inicialmente.

## Corte y resultados

Información completa: **junio de 2026**. Periodo común: enero de 2019–junio de 2026, 90 meses y seis componentes. Último mes parcial: julio de 2026, con cemento y sacrificio vacuno observados. Las series utilizadas no incluyen observaciones posteriores al sismo del **10 de agosto de 2026**.

| Indicador | Nivel (2019=100) | Mensual | Anual |
|---|---|---|---|
| IREC | 117,07 | +1,08 % | +7,97 % |

Los porcentajes mensuales comparan con el mes inmediatamente anterior. Los anuales comparan con el mismo mes del año anterior. Los valores históricos se calculan con la muestra de la versión vigente y pueden revisarse. El IREC se normaliza a **promedio de 2019 = 100**; no se fija cada mes de 2019 en 100.

## Fuentes y selección de la batería

| Componente | Fuente | Unidad original | Historia disponible | Peso en el IREC | Enlace |
|---|---|---|---|---|---|
| Industria | DANE · EMMET | Índice de producción real, 2018 = 100 | enero de 2018 – junio de 2026 | 25,0 % | https://www.dane.gov.co/index.php/estadisticas-por-tema/industria/encuesta-mensual-manufacturera-con-enfoque-territorial-emmet |
| Cemento | DANE · ECG | Toneladas | abril de 2009 – julio de 2026 | 12,5 % | https://www.dane.gov.co/index.php/estadisticas-por-tema/construccion/estadisticas-de-cemento-gris |
| Área licenciada | DANE · ELIC | Metros cuadrados | enero de 2019 – junio de 2026 | 12,5 % | https://www.dane.gov.co/index.php/estadisticas-por-tema/construccion/licencias-de-construccion |
| Sacrificio vacuno | DANE · ESAG | Kilogramos en canal | enero de 2013 – julio de 2026 | 25,0 % | https://www.dane.gov.co/index.php/estadisticas-por-tema/agropecuario/encuesta-de-sacrificio-de-ganado |
| Exportaciones | Cámara de Comercio · Banrep | USD corrientes FOB | enero de 2013 – junio de 2026 | 12,5 % | https://suameca.banrep.gov.co/descarga-multiple-de-datos/ |
| Importaciones | Cámara de Comercio · Banrep | USD corrientes CIF | enero de 2013 – junio de 2026 | 12,5 % | https://suameca.banrep.gov.co/descarga-multiple-de-datos/ |

El archivo de Cámara de Comercio fue aportado como `Exportaciones.xlsx`. Las hojas `Exportaciones_historicas` e `Importaciones_historicas` contienen año, mes, valor corriente en dólares y peso bruto. Se confirmó que ambas corresponden a Caldas. El proyecto conserva el original y su copia de trabajo en `data/raw/camara_comercio/Exportaciones_actualizado.xlsx`. Esa fuente no tiene en este paquete una URL pública del archivo aportado.

Para industria se usa producción real, evitando incluir ventas y empleo industrial como tres votos del mismo sector. Para cemento se utiliza el total, sin sumar nuevamente sus desagregaciones. Para licencias se selecciona la cobertura de los 27 municipios desde 2019; no se empalma automáticamente con la cobertura municipal antigua. Sacrificio se mide por peso en canal y lugar de sacrificio. Los indicadores comerciales se conservan separados y las importaciones no se restan como en una identidad contable del PIB.

La batería descriptiva amplia se conserva en el proyecto, separada de los seis componentes de estimación. Los indicadores de Manizales o del Eje Cafetero y los trimestres móviles no se mezclan como observaciones mensuales departamentales. El periodo común empieza en 2019 por la disponibilidad de licencias con cobertura completa. Las historias anteriores se aprovechan para estimar la estacionalidad de cada serie.

El **PIB real departamental** se utiliza solamente para contraste anual. Fuente: [DANE, Cuentas nacionales departamentales](https://www.dane.gov.co/index.php/estadisticas-por-tema/cuentas-nacionales/cuentas-nacionales-departamentales). Se conserva la serie anual 1980–2025 en volumen encadenado, referencia 2015. No se utiliza PIB dentonizado como componente, objetivo de aprendizaje ni validación mensual.

### Corrección de exportaciones e importaciones

Los valores son USD corrientes FOB para exportaciones y CIF para importaciones. Se utilizaron por separado los índices encadenados de precios de exportación e importación del Banco de la República, **series 15361 y 15362**, disponibles desde enero de 1995 hasta junio de 2026 en el corte utilizado. La corrección cubre los 162 meses de cada flujo de Caldas, enero de 2013–junio de 2026.

```text
P_it_base = 100 × P_it / promedio(P_i en los 12 meses de 2019)
USD_2019_aproximados_it = USD_corrientes_it × 100 / P_it_base
```

Los precios están construidos a partir de valores en dólares; no se convierten previamente los flujos a pesos ni se usa IPC colombiano. Tampoco se usa el cociente de términos de intercambio como deflactor de ambos flujos. Son deflactores **nacionales**: la canasta de Caldas difiere de la colombiana. Además, las importaciones del archivo son CIF y el marco de precios del Banco utiliza valores FOB, de modo que el ajuste no separa fletes y seguros. El resultado es una aproximación en USD de 2019, no un índice departamental de volumen a composición constante.

En el archivo, `4_caldas_posar` concilia por mes con el total exportado de 2025. `3B_caldas_meses_cuci` concilia 24 meses: 2023 y 2025; no contiene 2024. La principal partida de café sin tostar representa 56,04 % de las exportaciones de 2025 y la de café soluble liofilizado, 15,35 %. No se aplicaron estas participaciones retrospectivamente a 2013–2026. Los subtotales de `999_caldas_país_producto` no coinciden con el total histórico disponible y no se distribuyeron artificialmente entre meses. No se identificó una hoja equivalente de productos importados en la versión suministrada.

Fuente de precios: [descarga de series Banrep](https://suameca.banrep.gov.co/descarga-multiple-de-datos/). [Guía metodológica de índices encadenados de precios del comercio exterior](https://www.banrep.gov.co/sites/default/files/ITI_1._Gu%C3%ADa_metodol%C3%B3gica_web%20_V1.pdf).

## Preparación econométrica

1. Verificación de fechas mensuales, claves únicas, continuidad y valores positivos. Las ausencias no se sustituyen por cero.
2. Ajuste **STL robusto sobre logaritmos**, periodo 12 y ventana estacional 13. Se utiliza la historia disponible de cada serie hasta el corte y se resta exclusivamente la estacionalidad. Se conservan tendencia e irregular, incluidos los choques. No hay recorte, winsorización ni eliminación de valores extremos. No se incluyen regresores específicos de Semana Santa o días hábiles.
3. Para el factor: `g_it = 100 × Δlog(y_it ajustado)` y `z_it = (g_it − media_i) / desviación_i`. Se utiliza primera diferencia, no diferencias de orden superior. Las medias y desviaciones corresponden a la muestra de entrenamiento.
4. Se preservan niveles, transformaciones y escalas. ADF y KPSS se usan como diagnósticos, no como reglas automáticas de eliminación. Los p-valores de KPSS están acotados por las tablas del método.

### IREC: compuesto por bloques

Cada bloque recibe 25 %. Los dos indicadores de construcción reciben 12,5 % cada uno, al igual que los dos comerciales. Son pesos analíticos explícitos, no ponderaciones extraídas del PIB.

```text
C_t = exp(Σ_i w_i × log(y_it ajustado))
IREC_balance_t = 100 × C_t / promedio(C en 2019)
```

Al excluir comercio exterior quedan tres bloques con un tercio cada uno. El indicador utiliza las seis series de manera continua; los componentes no entran y salen por disponibilidad de una publicación. Los meses incompletos se tratan aparte.

Los aportes del gráfico público se expresan en puntos porcentuales para facilitar la lectura. Parten de `a_it = 100 × w_i × Δlog(y_it ajustado)`, cuya suma es `L_t`. Se aplica a cada aporte el factor común `expm1(L_t/100)/(L_t/100)`, con límite 1 cuando `L_t = 0`. Así, los aportes suman exactamente `100 × expm1(L_t/100)`, la variación mensual aritmética del balance. Es una descomposición proporcional de la media geométrica; no son aportes al PIB ni efectos causales. La tabla de trabajo conserva los aportes originales en puntos logarítmicos.

### Factor dinámico: herramienta interna

```text
z_it = λ_i f_t + u_it
f_t = φ1 f_(t−1) + φ2 f_(t−2) + η_t
u_it = ρ_i u_i(t−1) + ε_it
```

Se compararon factores AR(1) y AR(2), con errores propios AR(1), innovaciones idiosincráticas diagonales y estacionariedad impuesta. Se estimó por máxima verosimilitud mediante filtro de Kalman. L-BFGS es el optimizador inicial; ante falta de convergencia se intenta Powell seguido de L-BFGS. La extensión AR(1) de los errores respondió a autocorrelación residual y a una concentración casi total de la especificación inicial en industria.

El BIC favorece el factor AR(2) entre las versiones completas. Los BIC de cuatro y seis componentes no se comparan directamente porque cambia el conjunto de variables.

| Modelo | Convergió | BIC | Menor varianza propia | Raíz dinámica máxima |
|---|---|---|---|---|
| factor_completo_ar1 | True | 1.373,160 | 0,001807 | 0,967687 |
| factor_completo_ar2 | True | 1.367,517 | 0,105028 | 0,653197 |
| factor_sin_comercio_ar1 | True | 897,704 | 0,232154 | 0,637841 |
| factor_sin_comercio_ar2 | True | 892,821 | 0,239107 | 0,636467 |

El diagnóstico interno conserva el **factor filtrado**. Este no aparece como un segundo índice en el HTML. Para expresarlo en unidades de crecimiento del agregado por bloques se aplica:

```text
g_comun_t = Σ_i w_i × media_i + (Σ_i w_i × desviación_i × λ_i) × f_t
I_t_prebase = exp(Σ_s≤t g_comun_s / 100)
Factor_interno_t = 100 × I_t_prebase / promedio(I_prebase en 2019)
```

Se ancla la acumulación en enero de 2019 y luego se normaliza. Esta escala representa la proyección común del agregado elegido; no estima crecimiento del PIB. Los movimientos propios `u_it` no entran en este índice, aunque sí participan en el pronóstico de los componentes. La estimación de parámetros y estacionalidad con la muestra vigente implica revisiones históricas; una serie filtrada no equivale automáticamente a las cifras que se habrían publicado en tiempo real.

### Parámetros del modelo auxiliar de pronóstico

| Parámetro | Estimación | Error estándar |
|---|---|---|
| loading.f1.industria_produccion_real | 0,822628 | 0,251951 |
| loading.f1.cemento_total | 0,706876 | 0,178286 |
| loading.f1.licencias_caldas_cobertura_nacional_area_total | 0,163326 | 0,100205 |
| loading.f1.sacrificio_vacuno_peso_canal | 0,458535 | 0,204363 |
| loading.f1.exportaciones_usd_2019_aprox | 0,270965 | 0,208506 |
| loading.f1.importaciones_usd_2019_aprox | 0,125668 | 0,153962 |
| sigma2.industria_produccion_real | 0,105028 | 0,185665 |
| sigma2.cemento_total | 0,361443 | 0,122364 |
| sigma2.licencias_caldas_cobertura_nacional_area_total | 0,582730 | 0,096085 |
| sigma2.sacrificio_vacuno_peso_canal | 0,596133 | 0,090862 |
| sigma2.exportaciones_usd_2019_aprox | 0,670833 | 0,101539 |
| sigma2.importaciones_usd_2019_aprox | 0,746956 | 0,124172 |
| L1.f1.f1 | -0,020171 | 0,166374 |
| L2.f1.f1 | -0,370955 | 0,126020 |
| L1.e(industria_produccion_real).e(industria_produccion_real) | -0,653197 | 0,355946 |
| L1.e(cemento_total).e(cemento_total) | -0,383136 | 0,202649 |
| L1.e(licencias_caldas_cobertura_nacional_area_total).e(licencias_caldas_cobertura_nacional_area_total) | -0,636452 | 0,083454 |
| L1.e(sacrificio_vacuno_peso_canal).e(sacrificio_vacuno_peso_canal) | -0,425362 | 0,107948 |
| L1.e(exportaciones_usd_2019_aprox).e(exportaciones_usd_2019_aprox) | -0,512680 | 0,096965 |
| L1.e(importaciones_usd_2019_aprox).e(importaciones_usd_2019_aprox) | -0,482272 | 0,117111 |

### Cargas y residuos

| Componente | Carga orientada | Correlación con factor | Ljung–Box p (12 rezagos) |
|---|---|---|---|
| industria_produccion_real | 0,822628 | 0,968351 | 0,802035 |
| cemento_total | 0,706876 | 0,790317 | 0,966730 |
| licencias_caldas_cobertura_nacional_area_total | 0,163326 | 0,083222 | 0,040776 |
| sacrificio_vacuno_peso_canal | 0,458535 | 0,542459 | 0,003863 |
| exportaciones_usd_2019_aprox | 0,270965 | 0,332775 | 0,435761 |
| importaciones_usd_2019_aprox | 0,125668 | 0,194291 | 0,159054 |

La asociación más alta se presenta con industria. Persisten señales de autocorrelación en licencias y sacrificio vacuno al nivel individual del 5 %; son diagnósticos exploratorios, sin ajuste por comparaciones múltiples. Estas limitaciones se conservan como parte de la evaluación y no se ocultan por el hecho de que los modelos converjan.

## Evaluación fuera de muestra

Se hicieron doce pronósticos a un mes, julio de 2025–junio de 2026. Para cada mes objetivo se truncaron los datos antes de ese mes y se reestimaron STL, escalas y parámetros. Para recuperar el nivel del mes pronosticado se utilizó el último ciclo estacional conocido. La evaluación emplea las versiones actuales de las fuentes, no archivos históricos de cada publicación ni calendarios de divulgación escalonada.

Las referencias son: mismo mes del año anterior, último nivel ajustado y AR(1) por componente. Los errores se estandarizan por la variabilidad de la serie en la muestra de entrenamiento. Se comparan los mismos meses y variables; cualquier fallo de convergencia se registra. En este corte los doce meses son comparables.

| Método | Meses | RMSE estandarizado | RMSE del agregado (puntos log.) |
|---|---|---|---|
| ar1_por_componente | 12 | 1,168454 | 14,424118 |
| factor_completo_ar1 | 12 | 1,159732 | 14,566241 |
| factor_completo_ar2 | 12 | 1,163410 | 13,979986 |
| ingenuo_estacional | 12 | 1,133171 | 13,447842 |
| persistencia_ajustada | 12 | 1,307728 | 13,939870 |

La documentación técnica conserva la comparación del nivel observado con el nivel estimado a un mes. Los pronósticos originales por componente, guardados en `evaluacion_pronosticos_detalle.csv`, se agregan con los pesos del IREC. Para cada corte se reconstruyen STL y la base utilizando únicamente los meses anteriores al objetivo:

```text
S_objetivo = estacionalidad del mismo mes del último ciclo disponible al corte
C_base = promedio en 2019 de exp(Σ_i w_i × log(nivel_ajustado_i al corte))
IREC_observado = 100 × exp(Σ_i w_i × (log(nivel_observado_i) − S_objetivo_i)) / C_base
IREC_estimado = 100 × exp(Σ_i w_i × (log(nivel_pronosticado_i) − S_objetivo_i)) / C_base
Diferencia_puntos = IREC_estimado − IREC_observado
```

La estacionalidad y la base de cada mes son iguales para observado y estimado, y para todos los métodos. Se mantiene así una escala comparable sin introducir meses posteriores en la estimación. El observado de esta prueba puede diferir de la serie histórica revisada del gráfico principal. Cada punto estimado es un pronóstico independiente a un mes; la línea no representa una proyección acumulada de doce meses.

`evaluacion_irec_observado_estimado.csv` conserva los 60 pares (cinco métodos × doce meses), su corte y diferencias. Se verifica que `100 × log(estimado/observado)` reproduzca el error agregado del paso 33, y que su RMSE coincida con la tabla anterior. El HTML no incluye esta comparación ni sus controles. Se conserva a continuación el detalle del método utilizado para completar y proyectar el IREC; las cinco alternativas permanecen en los resultados internos. Las diferencias son estimado menos observado, en puntos del índice, y no un porcentaje de precisión.

| Mes | Información hasta | IREC observado | IREC estimado | Diferencia (puntos) |
|---|---|---|---|---|
| julio de 2025 | junio de 2025 | 122,50 | 96,32 | -26,19 |
| agosto de 2025 | julio de 2025 | 103,28 | 113,80 | 10,52 |
| septiembre de 2025 | agosto de 2025 | 101,22 | 103,92 | 2,70 |
| octubre de 2025 | septiembre de 2025 | 108,58 | 106,83 | -1,75 |
| noviembre de 2025 | octubre de 2025 | 103,21 | 106,77 | 3,55 |
| diciembre de 2025 | noviembre de 2025 | 91,46 | 102,80 | 11,34 |
| enero de 2026 | diciembre de 2025 | 134,45 | 100,94 | -33,51 |
| febrero de 2026 | enero de 2026 | 118,62 | 102,41 | -16,21 |
| marzo de 2026 | febrero de 2026 | 125,37 | 106,01 | -19,36 |
| abril de 2026 | marzo de 2026 | 105,71 | 119,63 | 13,92 |
| mayo de 2026 | abril de 2026 | 115,14 | 108,88 | -6,27 |
| junio de 2026 | mayo de 2026 | 112,84 | 109,03 | -3,81 |

En enero de 2026 la estimación quedó 24,93 % por debajo del observado de la prueba; en febrero, 13,66 % por debajo. Estas brechas evalúan el pronóstico auxiliar y no son diferencias entre dos índices públicos. El RMSE agregado del método elegido fue 13,98 puntos logarítmicos, frente a 13,45 de la referencia del mismo mes del año anterior; no se afirma una ventaja predictiva.

La evaluación utiliza las versiones actuales de las fuentes, no archivos históricos de publicación. No se interpreta el mejor BIC como garantía de precisión predictiva; doce meses constituyen una evaluación inicial.

### Robustez y contraste anual

Se conservan internamente los modelos factoriales sin exportaciones e importaciones. La prueba desplegable del HTML compara el IREC con una variante del compuesto que excluye comercio y redistribuye pesos entre tres bloques iguales. Es una prueba de sensibilidad, no otro indicador de cabecera. No identifica exclusivamente el efecto del deflactor.

El contraste anual compara el crecimiento del promedio de doce meses de los índices con el crecimiento del PIB real departamental. Hay seis variaciones comparables, 2020–2025; incluyen pandemia y recuperación. No se fuerza el ajuste del índice a esos seis valores.

| Año | IREC (%) | Factor interno (%) | PIB real DANE (%) |
|---|---|---|---|
| 2020 | -5,90 | -2,17 | -5,14 |
| 2021 | 14,20 | 15,50 | 10,43 |
| 2022 | 1,83 | 3,25 | 6,03 |
| 2023 | -11,31 | -4,36 | 0,68 |
| 2024 | -2,93 | -3,53 | 1,81 |
| 2025 | 10,86 | 6,32 | 2,44 |

## Estimación inicial y proyección

Julio incorpora cemento y sacrificio vacuno; las otras cuatro series permanecen como faltantes. Se mantienen parámetros, medias y escalas de junio. La estacionalidad de julio se proyecta repitiendo el último ciclo estimado. Kalman actualiza el estado con los dos datos disponibles. En los paneles de esos dos componentes se utiliza exactamente ese ajuste para mostrar julio.

Se proyectan **agosto, septiembre y octubre de 2026**. El modelo auxiliar estima los movimientos comunes y propios de cada componente. Para julio se conservan los dos datos disponibles y se estiman los cuatro pendientes. Para los meses siguientes se proyectan los seis. En todos los casos se aplica la misma agregación geométrica y los mismos pesos del IREC; no se empalma la historia del compuesto con el índice factorial. Las fuentes originales conservan los valores faltantes.

El punto central es la **mediana condicional del nivel**, obtenida al exponenciar la media del crecimiento logarítmico acumulado. No se confunde con la esperanza aritmética de una variable lognormal. Las variaciones proyectadas comparan medianas de niveles.

La rutina interna conserva dos acumuladores de crecimiento, uno para el diagnóstico factorial y otro para el compuesto. El HTML utiliza exclusivamente el segundo, que corresponde al IREC. Si `a_t` es el estado, `T` la transición y `B` las filas que proyectan su crecimiento:

```text
Estado ampliado = [a_t, crecimiento común acumulado, crecimiento del balance acumulado]
A = [[T, 0], [B T, I]]
Q_ampliada = [I; B] R Q R' [I; B]'
P_(t+1) = A P_t A' + Q_ampliada
Límites del nivel = I_junio × exp((media acumulada ± 1,95996398454 × desvío acumulado) / 100)
```

La covarianza inicial incorpora la incertidumbre del estado filtrado de julio y su covarianza con el crecimiento acumulado. El último índice completo se trata como ancla conocida. Las bandas incluyen incertidumbre del estado parcial e innovaciones futuras **condicionadas a parámetros, precios y estacionalidad fijos**. Excluyen incertidumbre de estimación de parámetros, elección del modelo, deflactores, ajuste estacional y revisiones de fuentes. No son intervalos del efecto del sismo.

| Mes | Indicador | Estado | Nivel | Límite inferior 95 % | Límite superior 95 % |
|---|---|---|---|---|---|
| julio de 2026 | IREC | estimacion_parcial | 114,83 | 96,65 | 136,42 |
| agosto de 2026 | IREC | proyeccion | 117,98 | 92,48 | 150,53 |
| septiembre de 2026 | IREC | proyeccion | 117,76 | 86,86 | 159,66 |
| octubre de 2026 | IREC | proyeccion | 117,48 | 84,39 | 163,56 |

El modelo no impone un daño ni un rebote por el sismo. La línea del 10 de agosto ubica el evento en la cronología; no altera valores ni produce una discontinuidad artificial. Los datos son mensuales y los puntos se ubican en el inicio del mes para la visualización, sin implicar medición diaria. La proyección es una trayectoria basada en información previa al evento y deberá actualizarse al recibir cifras posteriores.

## Reproducción y actualización

En el **proyecto de trabajo** se mantienen `data/raw`, `data/processed`, `data/metadata`, `config`, `scripts`, `templates` y una única carpeta `outputs/modelos/vigente`. Los scripts y las fuentes originales no forman parte de estos dos archivos de publicación. Para reestimar los modelos se necesita ese proyecto; este paquete permite reproducir la visualización y consultar los datos publicados, pero no sustituye los microdatos ni el entorno de estimación.

Entorno: Python 3.12, NumPy 2.3.5, pandas 2.3.3, SciPy 1.16.3, statsmodels 0.14.6 y Matplotlib 3.10.8; versiones completas en `requirements-modelos-lock.txt` del proyecto. Se fija la semilla 20260910 y un hilo numérico. La ejecución previa de los modelos se repitió con igualdad exacta de los CSV numéricos.

| Rutina del proyecto | Función |
|---|---|
| `08_precios_comercio.py` | Adquirir índices de precios y conservar su procedencia |
| `10_organizar_series.py` y `11_comercio_bateria_indice.py` | Organizar fuentes, deflactar comercio y preparar la batería |
| `30_preparar_modelos.py` | Auditar, ajustar estacionalidad y transformar |
| `31_indice_compuesto.py` | Calcular balances completos y sin comercio |
| `32_factores_dinamicos.py` | Estimar factores y actualizar mes parcial |
| `33_evaluar_modelos.py` | Evaluar pronósticos, robustez y contraste con PIB |
| `34_reportar_modelos.py` y `35_verificar_modelos.py` | Generar resultados técnicos y comprobar consistencia |
| `36_proyectar_indices.py` | Proyectar índices e intervalos condicionales |
| `37_publicar_html.py` | Generar este HTML y README desde la plantilla y resultados |
| `38_verificar_publicacion.py` | Validar datos publicados, recursos incrustados y JavaScript |
| `39_ejecutar_modelos.py` | Coordinar la ejecución numerada y actualizar únicamente la versión vigente |

Desde PowerShell, en el proyecto de trabajo:

```powershell
# Recalcular los modelos y actualizar la publicación desde las bases preparadas:
.\EJECUTAR_MODELOS.ps1

# Actualizar proyecciones y publicación sin reestimar parámetros:
.\EJECUTAR_MODELOS.ps1 -Desde 36 -Hasta 38
```

Antes de una actualización estadística hay que incorporar y verificar las nuevas fuentes y regenerar la batería. El botón de proyección del HTML solo cambia la visualización: no descarga información ni reestima modelos. Tras regenerar, reemplazar `index.html` y `README.md` en el repositorio de publicación.

Los datos visibles están incorporados en el elemento `<script type="application/json" id="irec-data">`. Para extraerlos sin ejecutar JavaScript puede utilizarse Python estándar:

```python
from pathlib import Path
import json, re
page = Path('index.html').read_text(encoding='utf-8')
match = re.search(r'<script type="application/json" id="irec-data">(.*?)</script>', page, re.S)
data = json.loads(match.group(1))
```

## Referencias de implementación

- [statsmodels: DynamicFactor](https://www.statsmodels.org/v0.14.6/generated/statsmodels.tsa.statespace.dynamic_factor.DynamicFactor.html).
- [statsmodels: STL](https://www.statsmodels.org/v0.14.6/generated/statsmodels.tsa.seasonal.STL.html).
- [statsmodels: resultados del filtro de Kalman](https://www.statsmodels.org/v0.14.6/generated/statsmodels.tsa.statespace.kalman_filter.FilterResults.html).
- DANE y Banco de la República: enlaces de fuentes y metodología señalados arriba.

Los logotipos y la imagen de la estrategia corresponden a la identidad suministrada de la Gobernación de Caldas. Los cálculos del IREC son los del proyecto y no deben atribuirse al DANE o al Banco de la República como un indicador oficial de esas entidades.
