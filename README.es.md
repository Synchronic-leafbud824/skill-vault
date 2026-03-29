# Skill Vault

**Tu biblioteca personal de skills para Claude Code.**

[Read this in English](README.md)

---

## Que es esto?

Imagina que tienes una caja grande de juguetes, pero en lugar de juguetes, guarda **skills** — habilidades especiales que hacen a Claude Code mas inteligente.

La gente comparte miles de skills en internet todos los dias. El problema? Estan regados por todos lados. Encuentras uno en GitHub, otro en skills.sh, otro que alguien compartio en X... y luego olvidas donde los guardaste. O peor — algunos pueden ser daninos.

**Skill Vault** es tu caja de juguetes organizada y segura para skills. Hace tres cosas:

1. **Guarda y organiza** tus skills en carpetas etiquetadas
2. **Revisa cada skill** antes de guardarlo (como un guardia de seguridad para tu computadora)
3. **Te ayuda a encontrar el skill correcto** cuando estas construyendo algo

Eso es todo. Clonalo, abrelo con Claude, y empieza a coleccionar.

---

## Como Empezar

```bash
git clone https://github.com/Hainrixz/skill-vault.git
cd skill-vault
claude
```

Sin instalaciones. Sin configuracion. Sin dependencias. Solo abrelo y listo.

---

## Como Funciona

Cuando abres este proyecto con Claude Code, el agente **Vault Master** toma el control. Piensa en el como tu bibliotecario personal que:

- **Acepta skills** de cualquier lugar — pega una URL, pega el contenido, o solo dile el nombre
- **Analiza cada skill** con una lista de verificacion de seguridad de 13 puntos y lo califica: SEGURO, PRECAUCION o PELIGROSO
- **Lo archiva** en la carpeta de categoria correcta automaticamente
- **Encuentra skills para ti** cuando describes lo que estas construyendo

### Comandos

| Comando | Que hace |
|---------|----------|
| `/vault-add` | Guardar un nuevo skill (desde URL, contenido pegado, o nombre) |
| `/vault-search` | Buscar en tu vault por palabra clave |
| `/vault-recommend` | Describe tu proyecto, recibe skills que te sirvan |
| `/vault-discover` | Encontrar nuevos skills en internet |
| `/vault-list` | Ver todo lo que hay en tu vault |
| `/vault-stats` | Estadisticas del vault + verificacion de salud |
| `/vault-remove` | Eliminar un skill |

---

## Estructura de Carpetas

Los skills se guardan en carpetas por categoria. Cada skill tiene su propio archivo con metadata, analisis de seguridad, instrucciones de instalacion y el contenido original preservado.

```
categories/
├── automation/          # Bots de navegador, scripts, automatizaciones
├── code-quality/        # Linting, refactorizacion, revisiones
├── design-ui/           # Componentes UI, sistemas de diseno, CSS
├── devops-deploy/       # Docker, CI/CD, infraestructura
├── documentation/       # READMEs, docs de API, changelogs
├── organization/        # Gestion de proyectos, planificacion
├── productivity/        # Herramientas de texto, notas, flujos de trabajo
├── research/            # Investigacion web, recopilacion de datos
├── testing/             # Tests unitarios, E2E, QA
└── web-development/     # React, Next.js, Vue, APIs
```

No ves una categoria que encaje? El Vault Master crea nuevas automaticamente.

---

## Seguridad

Cada skill es escaneado antes de entrar a tu vault. El Vault Master revisa:

- Comandos peligrosos (`rm -rf`, ejecucion pipe-to-shell)
- Robo de credenciales (lectura de llaves SSH, tokens de AWS, API keys)
- Exfiltracion de datos (envio de tus archivos a servidores externos)
- Codigo ofuscado (payloads ocultos en base64 o hex)
- Permisos excesivamente amplios
- Intentos de inyeccion de prompts

| Calificacion | Que significa |
|--------------|--------------|
| **SEGURO** | Limpio — no se detectaron operaciones riesgosas |
| **PRECAUCION** | Algo de riesgo — revisa los hallazgos antes de usar |
| **PELIGROSO** | Bandera roja — se te advertira antes de guardarlo |

Metodologia completa en [`security-rubric.md`](security-rubric.md).

---

## Ejemplo de Uso

```
Tu:     /vault-add https://github.com/anthropics/skills/tree/main/skill-creator
Vault:  Analizando skill... Calificacion: SEGURO
        Guardado en: categories/productivity/skill-creator.md
        Agregado al catalogo.

Tu:     /vault-recommend Estoy construyendo una app e-commerce con Next.js
Vault:  De tu vault, te recomiendo:
        - shadcn-ui (design-ui) [SEGURO] — Componentes UI
        - playwright-cli (testing) [PRECAUCION] — Testing E2E
        - vercel-deploy (devops-deploy) [SEGURO] — Despliegue

Tu:     /vault-discover optimizacion SEO
Vault:  Encontre 3 skills en skills.sh:
        - seo-audit [SEGURO] — Analisis SEO tecnico
        - meta-tags-generator [SEGURO] — Meta tags automaticos
        Agregar alguno? (s/n)
```

---

## Contribuir

1. Haz fork de este repo
2. Agrega skills con `/vault-add` o crea entradas manualmente en `categories/` usando la plantilla en `templates/skill-entry.md`
3. Envia un PR

---

## Creado por

[Tododeia](https://todoia.com) — Construyendo herramientas para la comunidad de IA.

## Licencia

MIT
