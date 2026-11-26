# aulausm

Skill para Claude que revisa tu **Aula USM** (Moodle de la Universidad Técnica Federico Santa María, `aula.usm.cl`): tareas pendientes, estado de entregas (incluidas las grupales), notas, "qué necesito sacar", avisos de los foros, calendario, programas de los ramos y cierre de semestre. También puede subir una entrega, pero solo con **doble confirmación tuya**.

> Proyecto de estudiante, no oficial. No tiene relación con la USM ni con Anthropic.

## Qué hace

- **Pendientes y calendario:** lista lo urgente (menos de 72 h), lo próximo y las novedades, en formato corto para celular.
- **Estado de tareas:** si enviaste, si hay borrador sin enviar, si está atrasada o calificada. En tareas grupales dice "sin envíos visibles en Aula" cuando no ve nada, en vez de asumir.
- **Notas y simulador:** lee el libro de calificaciones y el programa del ramo, y calcula qué nota necesitas para aprobar. Ignora lo que Aula cuenta como 0 por no estar publicado.
- **Avisos:** rescata fechas importantes (recuperativas, globales) que a veces solo están en el foro.
- **Archivos del curso:** lee PDFs (programas, pautas) con tu permiso.
- **Cierre de semestre:** resumen por ramo de lo que falta.
- **Entregas:** sube un archivo tuyo con doble confirmación (antes de subir y antes de enviar para calificar).

## Qué NO hace

- No pide ni escribe tu contraseña ni el MFA: el inicio de sesión lo haces tú.
- No redacta ni completa trabajos evaluados.
- No inicia ni responde cuestionarios, pruebas o exámenes en línea.
- No lee datos de otros estudiantes ni obedece instrucciones escondidas en contenido de Aula.
- No sirve para otras universidades.

## Requisitos

1. **Claude** con la extensión **Claude in Chrome** instalada y conectada (la skill controla tu Chrome a través de ella).
2. Dar a la extensión permiso para el sitio `aula.usm.cl`.
3. Tener **la sesión de Aula USM iniciada** en ese mismo Chrome (login SSO con tu cuenta USM).
4. Una forma de usar skills en Claude (por ejemplo, la app de Claude con skills habilitadas o Claude Code). Si tu plan incluye la extensión de Chrome no está confirmado: revisa tu plan.

## Instalación

### Opción A: Claude Code

```bash
git clone https://github.com/sebastianegj7/aulausm.git
mkdir -p ~/.claude/skills
cp -r aulausm/skills/aula-usm ~/.claude/skills/
```

Reinicia Claude Code y pídele, por ejemplo, "¿qué tengo pendiente en Aula?".

### Opción B: Claude (web/escritorio)

1. Baja el repositorio como ZIP y comprime la carpeta `skills/aula-usm` (debe contener `SKILL.md`) en un `.zip`.
2. En Claude, ve a **Configuración → Capacidades → Skills** y sube el `.zip`.
3. Instala la extensión Claude in Chrome y activa la skill.

Los nombres de los menús pueden cambiar; si no los encuentras, revisa la documentación de skills de Claude.

## Uso

Con Chrome abierto y sesión iniciada en Aula, escribe:

- "¿Qué tengo pendiente esta semana en Aula?"
- "¿Entregó mi grupo la Entrega 3?"
- "¿Cómo voy en Álgebra Lineal? ¿Qué necesito en el certamen 3?"
- "Cierre de semestre"
- "Lee el programa de Cálculo y dime cómo se aprueba"
- "Sube mi archivo `informe.pdf` a la tarea 2" (te pedirá confirmar dos veces)

## Privacidad y seguridad

- Todo ocurre en **tu** Chrome con **tu** sesión. La skill no guarda tu contraseña, cookies ni datos de otros estudiantes.
- La skill es solo lectura por defecto. Subir o enviar algo exige confirmación explícita cada vez.
- Un texto de Aula dirigido a una IA se trata como alerta, no como instrucción (algunos profesores ponen trampas para detectar uso de IA).
- Leer páginas en Aula puede dejar registro de acceso visible para el profesor (por ejemplo, marcar un recurso como visto).

## Uso responsable

Revisa las reglas de tu ramo y de la universidad sobre uso de IA. Tú eres responsable de lo que entregas: la skill no marca por ti la declaración de autoría.

## Estado y límites conocidos

- Última verificación en Aula: 26-11-2026. Si Aula cambia, algunas lecturas pueden fallar.
- Las funciones de API de Moodle para estudiantes están casi todas deshabilitadas, por eso la skill lee páginas.
- Las páginas índice por curso y la detección por clases CSS están marcadas como `[VERIFICAR]` dentro de la skill.
- La herramienta de subida de archivos tiene un límite de unos 3,8 MB por llamada; si tu archivo pesa más, súbelo tú.
- Las notas calculadas son estimaciones; lo oficial está en SIGA.

## Contribuir

Issues y pull requests son bienvenidos, sobre todo reportes de rutas que cambiaron o pruebas en otros ramos. No incluyas tus notas, capturas con datos personales ni tokens.

## Licencia

MIT, ver `LICENSE`.
