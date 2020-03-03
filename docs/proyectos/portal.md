# Portal STIC

![](https://swnepal.com.np/wp-content/uploads/2017/10/documentation-banner.jpg)

## Enlaces

* [Repositorio](http://gitlab.ual.es/mtorres/portalstic)
* [Issues](http://gitlab.ual.es/mtorres/portalstic/issues)
* [Chat](https://chat.stic.ual.es/openstack/channels/portalstic)
* [Agenda](http://gitlab.ual.es/mtorres/portalstic/-/boards)
* [Sprints](http://gitlab.ual.es/mtorres/portalstic/-/milestones)
* [Drive - No disponible]()
* [Web](http://portal.stic.ual.es/)


## Descripción

Portal STIC nace de la necesidad de disponer un lugar de acceso unificado tanto a los proyectos desarrollados en el STIC como a recursos de información de interés (documentos, tutoriales, formación, presentaciones, ...).

El portal está desarrollado en [Markdown](https://markdown.es/) y está desplegado mediante [MkDocs](https://www.mkdocs.org/), un generador de sitios web estáticos. Se usa el tema [MkDocs Material](https://squidfunk.github.io/mkdocs-material/) para una mejor experiencia de usuario.
 
## Dirigido a

Miembros del STIC.

## Background

En el STIC se desarrollan gran cantidad de proyectos (con su documentación asociada), informes, presentaciones, y demás. Sin embargo, a veces no se sigue un criterio con cierto grado de consistencia para la creación de la documentación. Además, todos esos recursos están almacenados en plataformas diferentes (Alfresco, Redmine, GitLab, Wiki, Google Drive, Google Docs, ...), lo que dificulta su acceso.

El intento de disponer de una única herramienta o plataforma que sea válida para todos los documentos y todas las situaciones impide la consecución del objetivo perseguido, que es el tener acceso a la información de interés, independientemente del soporte o plataforma en el que esté almnacenado.

## Propuesta

Disponer de una plataforma que sea fácil de usar, sea rápida y permita un mantenimiento colaborativo.

En este sentido, Portal STIC está desarrollado como un conjunto de documentos `markdown` editables por los usuarios. La edición puede incluir contenido dentro de los propios archivos del portal o bien enlazar a las URL donde esté disponible el recurso.

El portal está disponible en un repositorio Git en [GitLab de desarrollo](http://gitlab.ual.es/mtorres/portalstic.git). Para editar el portal, se deberá hacer un _fork_ del repositorio del portal y solicitar la incorporación del cambio mediante _merge request_. Una vez aceptados los cambios, el portal se actualizará de forma automática tras unos instantes.

## Permisos y seguridad

* Acceso a la documentación a todo el personal del STIC
* Edición reservada a miembros del STIC con acceso a [GitLab de desarrollo](http://gitlab.ual.es/mtorres/portalstic.git).
* Habrá una o varias personas encargadas de controlar y validar el proceso de publicación mediante _merge request_.

## Interacciones

* **GitLab de desarollo**: Almacena el repositorio del portal

## Documentación

* [Sintaxis Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Here-Cheatsheet)
* [MkDocs](https://www.mkdocs.org/#getting-started)
* [Añadir páginas nuevas](https://www.mkdocs.org/#adding-pages)
* [Creación de notas, información, ... (Admonitions)](https://squidfunk.github.io/mkdocs-material/extensions/admonition/#usage)
* [Inserción de código fuente](https://squidfunk.github.io/mkdocs-material/extensions/codehilite/#usage)

