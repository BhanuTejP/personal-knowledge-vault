# Personal Knowledge Vault — Second Brain

A personal knowledge management system built with [Obsidian](https://obsidian.md/), combining **PARA** (Projects, Areas, Resources, Archives) for knowledge organization and **GTD** (Getting Things Done) for task/action management.

> **This is the `clean-start` branch** — a blank vault with the full folder structure, templates, dashboards, and pre-configured plugins, but no sample content. If you'd like to see the system working with example projects and tasks first, check out the [`main` branch](https://github.com/BhanuTejP/personal-knowledge-vault) instead.

## Contents

- [Vault Structure](https://claude.ai/chat/2ab440cb-5bc2-4457-818a-c2971ca3379b#vault-structure)
- [GTD Workflow](https://claude.ai/chat/2ab440cb-5bc2-4457-818a-c2971ca3379b#gtd-workflow)
- [PARA Decision Rule](https://claude.ai/chat/2ab440cb-5bc2-4457-818a-c2971ca3379b#para-decision-rule)
- [Dashboards](https://claude.ai/chat/2ab440cb-5bc2-4457-818a-c2971ca3379b#dashboards)
- [Naming Conventions](https://claude.ai/chat/2ab440cb-5bc2-4457-818a-c2971ca3379b#naming-conventions)
- [Tagging Strategy](https://claude.ai/chat/2ab440cb-5bc2-4457-818a-c2971ca3379b#tagging-strategy)
- [Plugin Stack](https://claude.ai/chat/2ab440cb-5bc2-4457-818a-c2971ca3379b#plugin-stack)
- [Obsidian Setup](https://claude.ai/chat/2ab440cb-5bc2-4457-818a-c2971ca3379b#obsidian-setup)
- [Git Workflow](https://claude.ai/chat/2ab440cb-5bc2-4457-818a-c2971ca3379b#git-workflow)
- [AI Agent Integration](https://claude.ai/chat/2ab440cb-5bc2-4457-818a-c2971ca3379b#ai-agent-integration)

## Vault Structure

```
personal-knowledge-vault/
├── 00-Inbox/              → GTD capture — everything lands here first
├── 01-Projects/           → Active, time-bound work (one folder per project)
├── 02-Areas/              → Ongoing life domains (Career, Finance, Health, etc.)
├── 03-Resources/          → Reference material + MOCs
├── 04-Archives/           → Completed/inactive (mirrored: Projects/, Areas/, Resources/)
├── 05-Daily-Notes/        → Daily journal
├── 06-Weekly-Notes/       → Weekly GTD reviews
├── 07-Monthly-Notes/      → Monthly reviews (finance, goals, project health)
├── 08-Yearly-Notes/       → Yearly goals & reviews
├── 09-People/             → Personal CRM — one note per person
├── 10-Books/              → Reading notes & book summaries
├── 11-Dashboards/         → Homepage, My Day/Week/Month/Year, GTD Process, Views
├── 98-Templates/          → Reusable note templates
├── 99-Attachments/        → Images, PDFs, screenshots
└── .obsidian/             → Obsidian configuration
```

## GTD Workflow

```
Capture (00-Inbox) → Clarify (GTD Process) → Organize → Reflect (Reviews) → Engage (Do)
```

### Task Format

```markdown
- [ ] Task description #context/computer 📅 2026-08-25 ⏫
```

> **Important:** A task only shows up in date-based dashboard sections (Due Today, Overdue, My Week) if it has a `📅 YYYY-MM-DD` due date. A checkbox with no date — even one written inside today's daily note — will _not_ appear in those sections. It will still appear in the **From Today's Note** section on Homepage and My Day, which matches on the note's date instead of the task's due date. See [Dashboards](https://claude.ai/chat/2ab440cb-5bc2-4457-818a-c2971ca3379b#dashboards) below.

|Symbol|Meaning|
|---|---|
|`- [ ]`|Todo|
|`- [/]`|In progress|
|`- [x]`|Done|
|`- [-]`|Cancelled|
|`- [w]`|Waiting for someone|
|`⏫`|High priority|
|`🔼`|Medium priority|
|`🔽`|Low priority|
|`📅 YYYY-MM-DD`|Due date|
|`⏳ YYYY-MM-DD`|Scheduled date|
|`🔁 every week`|Recurring|

### GTD Contexts

Use these tags to mark where/how a task can be done:

`#context/computer` · `#context/phone` · `#context/office` · `#context/errand` · `#context/home` · `#context/anywhere`

### GTD Lists

|List|How to tag|
|---|---|
|Next Actions|Any `- [ ]` task with a `#context/` tag|
|Waiting For|`- [w]` status + mention who|
|Someday/Maybe|Tag with `#someday`|

## PARA Decision Rule

Not sure where a note goes? Use this:

1. Has a **clear outcome and deadline** → `01-Projects/`
2. Is an **ongoing responsibility** → `02-Areas/`
3. Is **useful reference material** → `03-Resources/`
4. Is **no longer active** → `04-Archives/`
5. **Unsure or in a hurry** → `00-Inbox/`

## Dashboards

Dashboards live in `11-Dashboards/` and are powered by Dataview queries that update automatically. The Homepage and My Day dashboards use three task sections that look similar but pull from different data — worth understanding once so the empty states don't confuse you later:

|Section|What it shows|Query logic|
|---|---|---|
|🔴 **Overdue**|Tasks with a due date before today, from anywhere in the vault|`due < date(today)`|
|✅ **Due Today**|Tasks with a due date of exactly today, from anywhere in the vault|`due = date(today)`|
|📓 **From Today's Note**|Any open task written in today's daily note, whether or not it has a due date|`FROM "05-Daily-Notes" WHERE file.day = date(today)`|

A task with no `📅` due date will only ever show under **From Today's Note** — never under Overdue or Due Today, even if it was written today. This is expected: those two sections track deadlines, not capture date. If a checkbox never shows up where you expect it, check whether it has a due date first.

`Dataview: No results to show` under a section is not an error — it just means nothing currently matches that query. It's the correct empty state, not a sign something's broken.

## Naming Conventions

|Type|Format|Example|
|---|---|---|
|Daily notes|`YYYY-MM-DD`|`2026-08-22.md`|
|Weekly notes|`YYYY-[W]WW`|`2026-W34.md`|
|Monthly notes|`YYYY-MM`|`2026-08.md`|
|Yearly notes|`YYYY`|`2026.md`|
|Projects|Descriptive kebab-case folder|`auth-redesign/`|
|MOCs|`MOC - Topic`|`MOC - Angular.md`|
|Templates|`tpl-type`|`tpl-project.md`|
|People|First name or full name|`Priya.md`|

## Tagging Strategy

### Status Tags

`#status/active` · `#status/paused` · `#status/done` · `#someday`

### Type Tags

`#type/project` · `#type/meeting` · `#type/article` · `#type/adr` · `#type/book` · `#type/learning` · `#type/moc` · `#type/person` · `#type/goal`

### Topic Tags

`#engineering` · `#ai` · `#finance` · `#career` · `#angular` · `#python` · `#django` · `#writing`

### Context Tags (GTD)

`#context/computer` · `#context/phone` · `#context/office` · `#context/errand` · `#context/home` · `#context/anywhere`

## Plugin Stack

All seven plugins below ship pre-installed as files in `.obsidian/plugins/` — you don't need to search the Community Plugins browser. The only manual step is a one-time security click (see [Obsidian Setup](https://claude.ai/chat/2ab440cb-5bc2-4457-818a-c2971ca3379b#obsidian-setup)).

|Plugin|Purpose|
|---|---|
|**Dataview**|Powers all dashboard views and queries|
|**Tasks**|Global task management with statuses, priorities, recurring|
|**Templater**|Smart templates with auto-fill date/title|
|**Calendar**|Visual calendar sidebar for daily notes|
|**Periodic Notes**|Creates daily, weekly, monthly, and yearly notes from templates|
|**Kanban**|Board view for project stages|
|**Homepage**|Auto-open dashboard on launch|

> Community plugins are third-party code. Review what's included before enabling if you're security-conscious — all seven are well-established plugins with large user bases, but you should always know what's running in your vault.

## Obsidian Setup

Everything below is **pre-configured** in `.obsidian/`. On first open, Obsidian will show a banner: _"Community plugins are disabled for security."_ Click **Turn on community plugins** — this is the one manual step that can't be automated, and it only happens once. All seven plugins will already be enabled and configured after that click.

### Core Settings

|Setting|Value|
|---|---|
|Default location for new notes|`00-Inbox`|
|Default location for attachments|`99-Attachments`|
|Use `[[Wikilinks]]`|Enabled|

### Plugin Settings

> **Note:** Daily, weekly, monthly, and yearly notes are all handled by the **Periodic Notes** plugin — the core Daily Notes plugin is intentionally disabled to avoid the two plugins issuing duplicate/conflicting commands.

|Plugin|Setting|Value|
|---|---|---|
|Periodic Notes|Daily folder|`05-Daily-Notes`|
|Periodic Notes|Daily format|`YYYY-MM-DD`|
|Periodic Notes|Daily template|`98-Templates/tpl-daily-note`|
|Periodic Notes|Weekly folder|`06-Weekly-Notes`|
|Periodic Notes|Weekly format|`YYYY-[W]WW`|
|Periodic Notes|Weekly template|`98-Templates/tpl-weekly-review`|
|Periodic Notes|Monthly folder|`07-Monthly-Notes`|
|Periodic Notes|Monthly format|`YYYY-MM`|
|Periodic Notes|Monthly template|`98-Templates/tpl-monthly-review`|
|Periodic Notes|Yearly folder|`08-Yearly-Notes`|
|Periodic Notes|Yearly format|`YYYY`|
|Periodic Notes|Yearly template|`98-Templates/tpl-yearly-review`|
|Templates|Folder|`98-Templates`|
|Homepage|Note|`11-Dashboards/Homepage`|
|Homepage|Open on startup|Enabled|

## Git Workflow

```bash
# Daily commit
git add -A && git commit -m "vault: $(date +%Y-%m-%d)" && git push

# If a plugin stores API keys
echo ".obsidian/plugins/<plugin-name>/data.json" >> .gitignore
```

## AI Agent Integration

This vault is designed for AI agent access. Since everything is plain `.md` files on disk:

- **Claude Desktop / Claude Code** — filesystem connector or MCP server reads/writes directly
- **Any AI agent** — can create notes, process inbox, assist weekly reviews, research topics
- **No API, no auth, no rate limits** — just files