# UML-P02-IngenieriaInversa

##¿Qué tipo de relación existe entre Agenda y Contacto?

Agregación o composición dependiendo del diseño.
Una Agenda contiene muchos Contactos.
Si los Contactos solo existen dentro de la Agenda y se destruyen cuando la Agenda se destruye → Composición.
Si los Contactos pueden existir independientemente de la Agenda → Agregación.
Cardinalidad típica: 1 Agenda → 0..* Contactos.

##¿Qué tipo de relación existe entre Contacto y Teléfono?

Composición.
Un Contacto tiene uno o más Teléfonos.
Los Teléfonos no existen sin el Contacto.
Por eso se modela como composición en UML.
Cardinalidad típica: 1 Contacto → 0..* Teléfonos.

##¿Qué tipo de relación existe entre Contacto y Dirección?

Similar a Teléfono, usualmente Composición.
Cada Contacto puede tener una o varias Direcciones.
La dirección normalmente no tiene sentido sin un contacto específico.
Cardinalidad típica: 1 Contacto → 0..* Direcciones.

##¿Por qué los tipos TipoTelefono y TipoVia se modelan como enumerados?

TipoTelefono puede ser: Móvil, Fijo, Trabajo, etc.
TipoVia puede ser: Calle, Avenida, Plaza, Carretera, etc.
Son valores finitos, conocidos y no cambian dinámicamente, por eso se modelan como enum en UML y en código.
Permite validación automática y evita errores de ingreso de datos.

##¿Qué relaciones del diagrama son asociaciones simples y cuáles podrían interpretarse como agregación o composición?

Relación	Tipo de relación	Justificación
Agenda ↔ Contacto	Agregación/Composición	Los contactos dependen de la agenda, pero podrían existir fuera de ella (agregación) o no (composición).
Contacto ↔ Teléfono	Composición	Los teléfonos dependen completamente del contacto.
Contacto ↔ Dirección	Composición	Las direcciones dependen del contacto.
Contacto ↔ TipoTelefono	Asociación simple	Es solo un atributo que clasifica el teléfono, no contiene objetos independientes.
Dirección ↔ TipoVia	Asociación simple	Es solo un atributo que clasifica la dirección.
