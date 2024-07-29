![fondoMokeup](https://github.com/user-attachments/assets/5e9300da-57c9-4764-989d-9aac5eb069dd)

# Bienvenidos a Adventure Works: ¡Tu compañero en la exploración y el estilo de vida activo!

En Adventure Works, nos apasiona ofrecerte una experiencia única que te inspire a abrazar la aventura y la actividad al aire libre. Nos enorgullece presentarnos como tu destino definitivo para equiparte con los mejores productos y accesorios diseñados para tus aventuras, ya sea que estés escalando montañas, recorriendo senderos o simplemente disfrutando del aire libre.

Como empresa líder en la industria de los deportes y la recreación, en Adventure Works nos dedicamos a proporcionarte productos de la más alta calidad que no solo cumplen, sino que superan tus expectativas. Desde nuestras bicicletas de última generación hasta nuestros equipos de senderismo de vanguardia y una amplia gama de accesorios deportivos, cada artículo que ofrecemos está diseñado para brindarte rendimiento, durabilidad y estilo incomparables.

Nos enorgullecemos de ser más que una simple tienda; somos tu compañero en cada paso de tu viaje. Nuestro compromiso con la excelencia se extiende más allá de nuestros productos, ya que nos esforzamos por ofrecerte un servicio al cliente excepcional, asesoramiento experto y recursos inspiradores para que puedas aprovechar al máximo tus experiencias al aire libre.

En Adventure Works, creemos en fomentar un estilo de vida activo y saludable para todos. Ya seas un entusiasta del deporte experimentado o un novato que está dando sus primeros pasos en el mundo de la aventura, estamos aquí para acompañarte en cada paso del camino.

Así que únete a nosotros en esta emocionante aventura. ¡Descubre el mundo con Adventure Works y haz de cada día una nueva aventura!

## Documentación del proyecto

### Restauración de la base de datos y creación de copia de seguridad

- Se restauró la base de datos de `AdventureWorksDW2019` en SQL Server y se creó la copia de seguridad correspondiente para garantizar la integridad de los datos.

### Conexión con Power BI

- Se estableció una conexión a través del servidor con Power BI para acceder a la base de datos restaurada, permitiendo el análisis de datos.

### Selección de tablas

- Una vez obtenido el acceso a la base de datos de `AdventureWorksDW2019`, se seleccionaron las tablas relevantes para el proyecto.

### Transformación de datos

- Se procedió a realizar la transformación de datos correspondiente en cada una de las tablas, identificando y eliminando valores nulos o vacíos y aquellas columnas que no serían utilizadas en el análisis.

#### Tabla DimGeography

- Se eliminaron las columnas `FrenchCountryRegionName` y `SpanishCountryRegionName`.

#### Tabla DimSalesTerritory

- Se eliminó la fila 11 que no contenía valores significativos.

#### Tabla DIMPromotion

- Se eliminaron las columnas `FrenchPromotionName`, `SpanishPromotionName`, `FrenchPromoType`, `SpanishPromoType`, `SpanishPromotionCategory` y `FrenchPromotionCategory`.

#### Tabla DimProductSubcategory

- Se eliminó la primera fila que contenía valores nulos.

#### Tabla DimProduct

- Se eliminaron las columnas `SpanishProductName`, `FrenchProductName`, `FrenchDescription`, `ChineseDescription`, `ArabicDescription`, `HebrewDescription`, `ThaiDescription`, `GermanDescription`, `JapaneseDescription` y `TurkishDescription`.

#### Tabla FactInternetSales

- Se eliminaron las columnas `PromotionKey`, `SalesOrderLineNumber`, `RevisionNumber`, `OrderQuantity`, `UnitPriceDiscountPct` y `Discount`.

#### Tabla DimDate

- Se eliminaron las columnas `SpanishDayNameOfWeek`, `FrenchDayNameOfWeek`, `SpanishMonthName` y `FrenchMonthName`.

#### Tabla DimCustomer

- Se estableció la primera fila como encabezado, se eliminaron datos nulos y columnas irrelevantes como `Title`, `Suffix`, `Column18`, `SpanishEducation`, `FrenchEducation`, `SpanishOccupation`, `FrenchOccupation` y `Column31`.
- Se eliminó la columna `RegionalCode` después de unificar la tabla con `DimGeography` para mejorar la visualización.

### Combinación de columnas

- Se combinaron las columnas de las tablas `DimProductSubcategory` y `DimProductCategory` para simplificar la visualización y el análisis de datos.

### Creación de relaciones

- Se establecieron relaciones entre las tablas según las necesidades del análisis.

### Creación de medidas

- Se crearon medidas útiles para el análisis, como `Utilidad Bruta`, `Utilidad Neta`, `COGS`, `Ingresos`, `Productos Vendidos`, `Total de Clientes`, `Margen de Beneficio`, `Cantidad de Países`, `Ratio de Costo Operacional`, `Total de Envíos`, `Costo Total de Productos Vendidos` y `Cantidad de Productos Vendidos`…etc un total de casi 30 medidas para poder utilizar satisfactoriamente los datos.
