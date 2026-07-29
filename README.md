# Verdict / Causa Workspace

## Русскоязычный правовой контур

Вердикт — инфраструктура эволюционирующего юридического интеллекта, первое полноценное приложение которой создается для российской правовой системы на институте договорных отношений. Юридически значимые объяснения, причины выводов, предупреждения, governance-решения и audit-артефакты первого пакета формируются на русском языке. Английские machine IDs и поля API сохраняются только там, где это необходимо для совместимости и воспроизводимости.

Правило закреплено в [политике русского языка](docs/russian-language-policy.md).

Verdict / Causa Workspace is an early-stage open-source infrastructure project for auditable legal AI. It explores an evolving legal intelligence: a universal legal core, institutional packages, legal ontology, GraphRAG/RAG, governance workflows, a Management Plane, and formal consistency checks.

## What this project is

This project is a foundation for building legal AI systems whose reasoning can be inspected, challenged, versioned, and rolled back. It is designed around structured legal sources, candidate hypotheses, governance stages, institutional packages, and reproducible checks.

The long-term goal is not a single assistant, but infrastructure for legal reasoning systems that can evolve under explicit governance while preserving auditability, predictability, and rollback.

## What this project is not

This is not a generic legal chatbot, not a wrapper around an LLM, and not a production legal advice system.

It does not provide legal advice. It should not be used as a substitute for professional legal review.

## Core idea

Verdict / Causa Workspace separates legal AI infrastructure into a universal core and institution-specific packages. The core captures shared concepts such as sources, formalized norms, doctrine/meta-principles, case graphs, authority, temporal validity, confidence, auditability, and reproducibility.

Institutional packages provide vocabulary, authority model, temporal model, JSON schema, deterministic JSON-to-Z3 mapping rules, contradiction taxonomy, benchmark cases, red-team scenarios, confidence policies, and activation policies for specific legal institutes.

The governing concept is preserved in [docs/verdict-concept-v2-5.md](docs/verdict-concept-v2-5.md).

The first institutional package targets the Russian legal system. Stable machine IDs and API fields remain in English, while legally significant explanations, reasons, warnings, governance decisions, and audit artifacts are produced in Russian. See [docs/russian-language-policy.md](docs/russian-language-policy.md).

## Universal core and institutional packages

The universal core is intentionally jurisdiction-aware but not tied to a single legal domain. It is meant to support:

- legal source modeling;
- temporal validity;
- source hierarchy and authority;
- candidate legal hypotheses;
- GraphRAG/RAG retrieval;
- formal consistency checks;
- governance and rollback.

Institutional packages extend the core with domain-specific schemas, vocabularies, benchmark tasks, and review workflows.

## First institutional package: contractual relations

The first institutional package focuses on contractual relations: formation, change and termination, the general part of obligations, sale, supply, and liability for breach.

Релиз `contracts-ru-v0@0.18.0` добавляет контур допуска пилотных данных, который доказывает Этап 0 на максимально реалистичном споре о поставке, не обрабатывая реальные клиентские документы. Контур хранит только псевдонимные ссылки и хэши содержимого, фиксирует проверенное законное основание обработки и требует четырёх независимых согласований. Правила описаны в русской [спецификации допуска пилотных данных](docs/pilot-data-admission-spec.md).

Релиз `contracts-ru-v0@0.19.0` добавляет формальную модель действия договора во времени по статьям 425 и 433 ГК РФ: момент заключения, вступление в силу, обратное действие, истечение срока и сохранение ответственности за нарушение. Правила описаны в русской [спецификации действия договора во времени](docs/contract-temporal-effect-spec.md).

Релиз `contracts-ru-v0@0.20.0` добавляет формальную модель исковой давности по статьям 195–208 ГК РФ: начало течения, общий и специальный срок, предельный десятилетний срок, приостановление, перерыв, заявление стороны, восстановление и исключения. Правила описаны в русской [спецификации исковой давности](docs/contract-limitation-spec.md).

Релиз `contracts-ru-v0@0.21.0` добавляет формальную модель толкования договора по статье 431 ГК РФ: буквальное значение, сопоставление с договором в целом, действительную общую волю сторон и толкование против составителя. Правила описаны в русской [спецификации толкования договора](docs/contract-interpretation-spec.md).

Релиз `contracts-ru-v0@0.22.0` добавляет формальную модель формы сделки по статьям 158–165 и 434 ГК РФ: требуемую форму, допустимые способы соблюдения письменной формы и последствия её несоблюдения — лишение права ссылаться на свидетельские показания и ничтожность сделки. Правила описаны в русской [спецификации формы сделки](docs/contract-form-spec.md).

Релиз `contracts-ru-v0@0.23.0` добавляет формальную модель предварительного договора по статье 429 и пункту 4 статьи 445 ГК РФ: заключение и форму, определённость предмета основного договора, срок его заключения, уклонение стороны, понуждение к заключению и возмещение убытков, а также прекращение обязательств. Правила описаны в русской [спецификации предварительного договора](docs/contract-preliminary-spec.md).

Релиз `contracts-ru-v0@0.24.0` добавляет формальную модель договора в пользу третьего лица по статье 430 ГК РФ: право третьего лица требовать исполнения, связанность сторон после выражения намерения (необходимость согласия третьего лица на изменение и расторжение) и переход права к кредитору при отказе третьего лица. Правила описаны в русской [спецификации договора в пользу третьего лица](docs/contract-third-party-spec.md).

Релиз `contracts-ru-v0@0.25.0` добавляет формальную модель публичного договора по статье 426 ГК РФ: обязанность заключить договор с каждым обратившимся, недопустимость необоснованного отказа и предпочтения, единство условий и ничтожность условий, противоречащих публичному режиму. Правила описаны в русской [спецификации публичного договора](docs/contract-public-spec.md).

Релиз `contracts-ru-v0@0.26.0` добавляет формальную модель договора присоединения по статье 428 ГК РФ: режим присоединения, основания для изменения или расторжения (лишение обычных прав, исключение ответственности другой стороны, явно обременительные условия) и ограничение для присоединившегося предпринимателя. Правила описаны в русской [спецификации договора присоединения](docs/contract-adhesion-spec.md).

Релиз `contracts-ru-v0@0.27.0` добавляет формальную модель заверений об обстоятельствах по статье 431.2 ГК РФ: недостоверное заверение, имеющее значение, основание ответственности, возмещение убытков или неустойку, право на отказ от договора и оспаривание при обмане. Правила описаны в русской [спецификации заверений об обстоятельствах](docs/contract-representations-spec.md).

Релиз `contracts-ru-v0@0.28.0` добавляет формальную модель преддоговорной ответственности по статье 434.1 ГК РФ: недобросовестное ведение и прекращение переговоров, нарушение конфиденциальности, возмещение убытков независимо от заключения договора и ничтожность соглашений об ограничении такой ответственности. Правила описаны в русской [спецификации преддоговорной ответственности](docs/contract-precontractual-spec.md).

Релиз `contracts-ru-v0@0.29.0` добавляет формальную модель опциона на заключение договора и опционного договора по статьям 429.2 и 429.3 ГК РФ: безотзывную оферту и акцепт в срок, определённость условий и возмездность, право требовать по опционному договору, его прекращение по истечении срока и невозвратность платежа. Правила описаны в русской [спецификации опционных конструкций](docs/contract-option-spec.md).

Релиз `contracts-ru-v0@0.30.0` добавляет формальную модель рамочного договора (договора с открытыми условиями) и абонентского договора (договора с исполнением по требованию) по статьям 429.1 и 429.4 ГК РФ: определение общих условий, их конкретизацию отдельными договорами или заявками, применение общих условий к неурегулированным отношениям, право абонента требовать исполнение и обязанность вносить плату независимо от требования. Правила описаны в русской [спецификации рамочного и абонентского договора](docs/contract-framework-spec.md).

Релиз `contracts-ru-v0@0.31.0` добавляет формальную модель свободы договора и цены по статьям 421–424 ГК РФ: свободу заключения, непоименованный и смешанный договор, определение условий по усмотрению сторон, соответствие императивным нормам, действие принятого после заключения закона, презумпцию возмездности и определение цены исполнения. Правила описаны в русской [спецификации свободы договора и цены](docs/contract-freedom-spec.md).

Релиз `contracts-ru-v0@0.32.0` добавляет формальную модель заключения договора в обязательном порядке и на торгах по статьям 445–449 ГК РФ: понуждение обязанной стороны и возмещение убытков, определение спорных условий судом, заключение на торгах через протокол о результатах, уклонение победителя и недействительность торгов, проведённых с нарушением правил. Правила описаны в русской [спецификации порядка заключения договора](docs/contract-procedure-spec.md).

Релиз `contracts-ru-v0@0.33.0` добавляет формальную модель общих положений об обязательствах по статьям 307–308.3 ГК РФ: понятие обязательства и право кредитора требовать исполнения, добросовестность сторон, необязательность обязательства для не участвующих в нём лиц, альтернативные и факультативные обязательства и защиту прав кредитора — исполнение в натуре и судебную неустойку. Правила описаны в русской [спецификации общих положений об обязательствах](docs/contract-general-obligations-spec.md).

Релиз `contracts-ru-v0@0.34.0` добавляет формальную модель розничной купли-продажи по статьям 492–505 ГК РФ: публичность договора, заключение выдачей чека, обязанность предоставить информацию о товаре, права покупателя при ненадлежащем качестве, обмен товара надлежащего качества и возмещение разницы в цене. Правила описаны в русской [спецификации розничной купли-продажи](docs/contract-retail-sale-spec.md).

Релиз `contracts-ru-v0@0.50.0` добавляет формальную модель безвозмездного пользования (ссуды) по статьям 689–701 ГК РФ (глава 36): квалификацию, запрет коммерческой организации передавать имущество своему инсайдеру, обязанность предоставить вещь с принадлежностями, ответственность за умышленно скрытые недостатки, сохранение прав третьих лиц, обязанность ссудополучателя содержать вещь, распределение риска случайной гибели, основания досрочного расторжения, месячный срок извещения при отказе и сохранение прав при отчуждении вещи. Правила описаны в русской [спецификации безвозмездного пользования](docs/contract-gratuitous-use-spec.md).

Релиз `contracts-ru-v0@0.49.0` добавляет формальную модель найма жилого помещения по статьям 671–688 ГК РФ (глава 35): квалификацию, письменную форму, требование изолированного и пригодного для постоянного проживания помещения, обязанности наймодателя по эксплуатации и коммунальным услугам, нарушения нанимателя, недопустимость одностороннего изменения платы, преимущественное право на новый срок, судебный порядок расторжения и предоставление срока для устранения нарушения. Правила описаны в русской [спецификации найма жилого помещения](docs/contract-residential-lease-spec.md).

Релиз `contracts-ru-v0@0.48.0` добавляет формальную модель финансовой аренды (лизинга) по статьям 665–670 ГК РФ (глава 34, § 6): квалификацию, допустимость предмета лизинга, уведомление продавца о лизинговом назначении, последствия непередачи предмета в срок по обстоятельствам, за которые отвечает арендодатель, переход риска случайной гибели в момент передачи, прямые требования арендатора к продавцу и солидарную ответственность арендодателя при выборе им продавца. Этот выпуск завершает главу 34 ГК РФ «Аренда». Правила описаны в русской [спецификации финансовой аренды](docs/contract-leasing-spec.md).

Релиз `contracts-ru-v0@0.47.0` добавляет формальную модель аренды предприятий по статьям 656–664 ГК РФ (глава 34, § 5): квалификацию, письменную форму одного документа и недействительность при её несоблюдении, государственную регистрацию, письменное уведомление кредиторов, согласие кредитора на перевод долгов, передачу по передаточному акту и подготовку за счёт арендодателя, право арендатора распоряжаться материальными ценностями, обязанность по содержанию предприятия и подготовку к возврату за счёт арендатора. Правила описаны в русской [спецификации аренды предприятий](docs/contract-enterprise-lease-spec.md).

Релиз `contracts-ru-v0@0.46.0` добавляет формальную модель аренды зданий и сооружений по статьям 650–655 ГК РФ (глава 34, § 4): квалификацию, письменную форму одного документа и недействительность при её несоблюдении, государственную регистрацию при сроке не менее года, передачу прав на часть земельного участка, сохранение права пользования участком при смене собственника, существенное условие о размере арендной платы и оформление передачи и возврата передаточным актом. Правила описаны в русской [спецификации аренды зданий и сооружений](docs/contract-building-lease-spec.md).

Релиз `contracts-ru-v0@0.45.0` добавляет формальную модель аренды транспортных средств по статьям 632–649 ГК РФ (глава 34, § 3): квалификацию, письменную форму независимо от срока, неприменение преимущественного права, обязанность по содержанию и ремонту, предоставление услуг экипажа, распределение расходов по эксплуатации, обязанность по страхованию, право на субаренду и распределение ответственности за вред третьим лицам. Правила описаны в русской [спецификации аренды транспортных средств](docs/contract-vehicle-lease-spec.md).

Релиз `contracts-ru-v0@0.44.0` добавляет формальную модель проката по статьям 626–631 ГК РФ (глава 34, § 2): квалификацию проката, письменную форму, предельный срок до одного года, неприменение преимущественного права, распределение расходов на устранение недостатков, десятидневный срок устранения недостатков, возврат части платы при досрочном возврате, обязанность арендодателя по капитальному и текущему ремонту и запрет субаренды и передачи прав. Правила описаны в русской [спецификации проката](docs/contract-rental-spec.md).

Релиз `contracts-ru-v0@0.43.0` добавляет формальную модель общих положений об аренде по статьям 606–625 ГК РФ (глава 34, § 1): квалификацию аренды, определённость объекта, форму и государственную регистрацию, ответственность арендодателя за недостатки и предоставление имущества, предупреждение о правах третьих лиц, согласие на субаренду, обязанность по капитальному ремонту, досрочное расторжение при существенном нарушении арендатором, преимущественное право на новый срок и возмещение неотделимых улучшений. Правила описаны в русской [спецификации аренды](docs/contract-lease-spec.md).

Релиз `contracts-ru-v0@0.42.0` добавляет формальную модель ренты и пожизненного содержания с иждивением по статьям 583–605 ГК РФ (глава 33): квалификацию ренты, нотариальную форму и ничтожность при её несоблюдении, обеспечение выплаты и проценты за просрочку, ничтожность отказа от выкупа и выкуп постоянной ренты, расторжение пожизненной ренты при существенном нарушении и недопустимость обременения имущества пожизненного содержания без согласия получателя. Правила описаны в русской [спецификации ренты](docs/contract-annuity-spec.md).

Релиз `contracts-ru-v0@0.41.0` добавляет формальную модель договора дарения по статьям 572–582 ГК РФ (глава 32): квалификацию дарения, притворность при встречном предоставлении, требуемую письменную форму и ничтожность при её несоблюдении, запрещение и ограничения дарения, отказ одаряемого, отмену дарения с изъятием обычных подарков и отмену пожертвования при нарушении назначения. Правила описаны в русской [спецификации дарения](docs/contract-gift-spec.md).

Релиз `contracts-ru-v0@0.40.0` добавляет формальную модель договора мены по статьям 567–571 ГК РФ (глава 31): квалификацию мены, субсидиарное применение правил о купле-продаже, презумпцию равноценности и обязанность оплатить разницу в цене, встречное исполнение обязанности передать товар, одновременный переход права собственности и ответственность за изъятие товара третьим лицом. Правила описаны в русской [спецификации мены](docs/contract-barter-spec.md).

Релиз `contracts-ru-v0@0.39.0` добавляет формальную модель договора продажи предприятия по статьям 559–566 ГК РФ: квалификацию продажи предприятия как имущественного комплекса, письменную форму с приложениями и регистрацию договора, удостоверение состава, права кредиторов и солидарную ответственность за перевод долга без согласия, передачу по акту, регистрацию перехода права и уменьшение цены при неуказанных долгах. Правила описаны в русской [спецификации продажи предприятия](docs/contract-enterprise-sale-spec.md).

Релиз `contracts-ru-v0@0.38.0` добавляет формальную модель договора продажи недвижимости по статьям 549–558 ГК РФ: квалификацию продажи недвижимости, письменную форму одним документом, государственную регистрацию перехода права, определённость предмета и цены как условия заключённости, передачу по передаточному акту и последствия уклонения от него, последствия ненадлежащего качества и перечень лиц при продаже жилого помещения. Правила описаны в русской [спецификации продажи недвижимости](docs/contract-real-estate-sale-spec.md).

Релиз `contracts-ru-v0@0.37.0` добавляет формальную модель договора энергоснабжения по статьям 539–548 ГК РФ: квалификацию договора энергоснабжения, соответствие энергии договору по количеству и качеству, право абонента отказаться от оплаты некачественной энергии, обязанности по содержанию сетей и режиму потребления, оплату по данным учёта и правомерность перерыва подачи. Правила описаны в русской [спецификации энергоснабжения](docs/contract-energy-supply-spec.md).

Релиз `contracts-ru-v0@0.36.0` добавляет формальную модель договора контрактации по статьям 535–538 ГК РФ: квалификацию договора как контрактации, обязанность заготовителя принять сельскохозяйственную продукцию по месту нахождения производителя и недопустимость отказа от соответствующей продукции, условие о возврате отходов переработки, обязанность производителя передать продукцию в согласованном количестве и ассортименте и ответственность производителя только при наличии его вины. Правила описаны в русской [спецификации контрактации](docs/contract-contractation-spec.md).

Релиз `contracts-ru-v0@0.35.0` добавляет формальную модель поставки товаров для государственных и муниципальных нужд по статьям 525–534 ГК РФ: заключение государственного контракта и обязательность его заключения для поставщика, прикрепление покупателя и отказ покупателя от товаров, оплату по ценам контракта, поручительство заказчика и возмещение убытков поставщику. Правила описаны в русской [спецификации поставки для государственных нужд](docs/contract-state-supply-spec.md).

This is the first proving ground for the infrastructure, not the full scope of the project.

## Architecture

The initial architecture is organized around:

- Operational and generative contours;
- Universal Core;
- Knowledge Plane;
- Management Plane;
- Institutional Package Layer;
- Reasoning Layer;
- Governance Layer;
- Evaluation and Red Team Layer;
- Privacy and Tenant Safety Layer.

See [docs/architecture.md](docs/architecture.md) for details.

For Phase 0 implementation detail, see:

- [Phase 0 execution plan](docs/phase-0-execution-plan.md);
- [Universal core specification](docs/universal-core-spec.md);
- [Bootstrap pipeline specification](docs/bootstrap-pipeline-spec.md);
- [Management Plane specification](docs/management-plane-spec.md);
- [Translation Layer specification](docs/translation-layer-spec.md);
- [Bounded contractual counterfactual specification](docs/contract-counterfactual-spec.md);
- [Contract-formation prerequisite specification](docs/contract-formation-spec.md);
- [Transaction-invalidity specification](docs/contract-invalidity-spec.md);
- [Performance-security specification](docs/contract-security-spec.md);
- [Obligation-dynamics specification](docs/contract-obligation-dynamics-spec.md);
- [Performance and remedies specification](docs/contract-performance-remedies-spec.md);
- [General sale-contract specification](docs/contract-sale-spec.md);
- [Special supply-contract specification](docs/contract-supply-spec.md);
- [Contract change-and-termination specification](docs/contract-change-termination-spec.md);
- [Contractual liability and penalty prerequisite specification](docs/contract-liability-spec.md);
- [Evaluation and Red Team specification](docs/evaluation-and-red-team-spec.md);
- [Contracts RU v0 changelog](docs/contracts-ru-v0-changelog.md);
- [Contracts RU v0 compatibility matrix](docs/contracts-ru-v0-compatibility.md);
- [Phase 0 backlog](docs/phase-0-backlog.md).

## Governance and auditability

New legal hypotheses should not become active knowledge by default. They move through a governance pipeline that includes type classification, formal checks, source checks, benchmark checks, red-team testing, expert review, cross-review for high-impact candidates, sandboxing, activation, monitoring, revalidation, rejection, and rollback.

The current repository contains only the first skeleton of this workflow.

## Current status

This repository is at the early architectural/prototype stage. The project is not production-ready and should not be used as a substitute for legal advice. The current goal is to build an open-source foundation for auditable legal AI infrastructure.

## Roadmap

The roadmap starts with repository foundation and architecture, then moves toward Phase 0: universal core plus the first full institutional package for contractual relations. The true MVP is an auditable contradiction-aware legal reasoning engine with a working universal core, explicit Management Plane, and first institutional package.

See [docs/roadmap.md](docs/roadmap.md).

## Repository structure

```text
docs/       Architecture, concept, governance, security, roadmap.
examples/   Small example payloads for early prototypes.
scripts/    Repository and developer helper scripts.
src/causa/  Python package skeleton.
tests/      Minimal tests for the first models and pipeline.
```

## Development setup

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
pip install -e ".[dev]"
pytest
ruff check src tests
```

## Phase 0 synthetic trace

Generate the current synthetic supply-dispute trace:

```bash
python scripts/export_phase0_demo_trace.py
```

The output is written to `examples/phase0_supply_dispute_trace.json`. It is a non-production architecture demo, not legal advice.

Generate the standalone synthetic reviewed-input contract analysis:

```bash
python scripts/export_synthetic_reviewed_contract_analysis.py
```

The output is written to `examples/synthetic_reviewed_contract_analysis.json`.

Generate the synthetic Russian-language governance lifecycle report:

```bash
python scripts/export_synthetic_governance_lifecycle.py
```

The output is written to `examples/synthetic_governance_lifecycle_report.json`.

Generate the synthetic Russian-language Management Plane policy registry:

```bash
python scripts/export_synthetic_management_policy_registry.py
```

The output is written to `examples/synthetic_management_policy_registry_report.json`.

Generate the three-level Russian legal explanation with faithfulness and structural usability reports:

```bash
python scripts/export_synthetic_translation_bundle.py
```

The output is written to `examples/synthetic_translation_bundle_report.json`. Human usability still requires a lawyer pilot.

Generate the bounded contractual counterfactual report with dedicated benchmark and Red Team results:

```bash
python scripts/export_synthetic_counterfactual_evaluation.py
```

The output is written to `examples/synthetic_counterfactual_evaluation_report.json`. Every branch is hypothetical, budget-limited, and subject to lawyer review.

Generate the reviewed liability and penalty-reduction prerequisite report:

```bash
python scripts/export_synthetic_liability_evaluation.py
```

The output is written to `examples/synthetic_liability_evaluation_report.json`. It does not calculate a penalty reduction or predict a court outcome.

Generate the reviewed contract-formation prerequisite report:

```bash
python scripts/export_synthetic_formation_evaluation.py
```

The output is written to `examples/synthetic_formation_evaluation_report.json`. It checks offer, essential terms, form, and acceptance boundaries without deciding a court outcome.

Сформировать отчёт о действии договора во времени:

```bash
python scripts/export_synthetic_temporal_effect_evaluation.py
```

Результат записывается в `examples/synthetic_temporal_effect_evaluation_report.json`. Отчёт проверяет момент заключения, вступление в силу, обратное действие и окончание срока по статьям 425 и 433 ГК РФ и не подменяет судебную оценку.

Сформировать отчёт об исковой давности:

```bash
python scripts/export_synthetic_limitation_evaluation.py
```

Результат записывается в `examples/synthetic_limitation_evaluation_report.json`. Отчёт проверяет начало течения, срок, приостановление, перерыв и применение давности по статьям 195–208 ГК РФ и не подменяет судебную оценку.

Сформировать отчёт о толковании договора:

```bash
python scripts/export_synthetic_interpretation_evaluation.py
```

Результат записывается в `examples/synthetic_interpretation_evaluation_report.json`. Отчёт проверяет буквальное значение, сопоставление с договором в целом и действительную общую волю сторон по статье 431 ГК РФ и не подменяет судебную оценку.

Сформировать отчёт о форме сделки:

```bash
python scripts/export_synthetic_form_evaluation.py
```

Результат записывается в `examples/synthetic_form_evaluation_report.json`. Отчёт проверяет требуемую форму, соблюдение письменной и нотариальной формы и последствия её несоблюдения по статьям 158–165 и 434 ГК РФ и не подменяет судебную оценку.

Сформировать отчёт о предварительном договоре:

```bash
python scripts/export_synthetic_preliminary_evaluation.py
```

Результат записывается в `examples/synthetic_preliminary_evaluation_report.json`. Отчёт проверяет заключение и форму, определённость предмета основного договора, срок его заключения, понуждение к заключению и прекращение обязательств по статье 429 и пункту 4 статьи 445 ГК РФ и не подменяет судебную оценку.

Сформировать отчёт о договоре в пользу третьего лица:

```bash
python scripts/export_synthetic_third_party_evaluation.py
```

Результат записывается в `examples/synthetic_third_party_evaluation_report.json`. Отчёт проверяет право третьего лица требовать исполнения, связанность сторон после выражения намерения и переход права к кредитору по статье 430 ГК РФ и не подменяет судебную оценку.

Сформировать отчёт о публичном договоре:

```bash
python scripts/export_synthetic_public_contract_evaluation.py
```

Результат записывается в `examples/synthetic_public_contract_evaluation_report.json`. Отчёт проверяет обязанность заключить договор, недопустимость отказа и предпочтения, единство условий и ничтожность противоречащих условий по статье 426 ГК РФ и не подменяет судебную оценку.

Сформировать отчёт о договоре присоединения:

```bash
python scripts/export_synthetic_adhesion_evaluation.py
```

Результат записывается в `examples/synthetic_adhesion_evaluation_report.json`. Отчёт проверяет режим присоединения, основания для изменения или расторжения и ограничение для присоединившегося предпринимателя по статье 428 ГК РФ и не подменяет судебную оценку.

Сформировать отчёт о заверениях об обстоятельствах:

```bash
python scripts/export_synthetic_representations_evaluation.py
```

Результат записывается в `examples/synthetic_representations_evaluation_report.json`. Отчёт проверяет недостоверное заверение, основание ответственности, возмещение убытков, право на отказ от договора и оспаривание при обмане по статье 431.2 ГК РФ и не подменяет судебную оценку.

Сформировать отчёт о преддоговорной ответственности:

```bash
python scripts/export_synthetic_precontractual_evaluation.py
```

Результат записывается в `examples/synthetic_precontractual_evaluation_report.json`. Отчёт проверяет недобросовестное ведение переговоров, нарушение конфиденциальности, возмещение убытков и ничтожность ограничения ответственности по статье 434.1 ГК РФ и не подменяет судебную оценку.

Сформировать отчёт об опционных конструкциях:

```bash
python scripts/export_synthetic_option_evaluation.py
```

Результат записывается в `examples/synthetic_option_evaluation_report.json`. Отчёт проверяет действительность опциона, заключение основного договора акцептом, право по опционному договору и невозвратность платежа по статьям 429.2 и 429.3 ГК РФ и не подменяет судебную оценку.

Generate the reviewed contract change-and-termination report:

```bash
python scripts/export_synthetic_termination_evaluation.py
```

The output is written to `examples/synthetic_termination_evaluation_report.json`. It keeps agreement, judicial, and unilateral paths separate and does not predict a court outcome.

Generate the reviewed transaction-invalidity report:

```bash
python scripts/export_synthetic_invalidity_evaluation.py
```

The output is written to `examples/synthetic_invalidity_evaluation_report.json`. It distinguishes void and voidable grounds, procedure, and effects without replacing judicial assessment.

Generate the reviewed performance-security report:

```bash
python scripts/export_synthetic_security_evaluation.py
```

The output is written to `examples/synthetic_security_evaluation_report.json`. It keeps accessory security, independent guarantee, enforcement routes, and return consequences separate without deciding a court outcome.

Generate the reviewed obligation-dynamics report:

```bash
python scripts/export_synthetic_obligation_dynamics_evaluation.py
```

The output is written to `examples/synthetic_obligation_dynamics_evaluation_report.json`. It separates party changes from full and partial discharge paths without replacing judicial assessment.

Generate the reviewed performance-remedies report:

```bash
python scripts/export_synthetic_performance_remedies_evaluation.py
```

The output is written to `examples/synthetic_performance_remedies_evaluation_report.json`. It separates performance, delay, damages, interest, specific relief, and indemnity without calculating a court award.

Generate the reviewed general sale report for articles 454–491 of the Russian Civil Code:

```bash
python scripts/export_synthetic_sale_evaluation.py
```

The output is written to `examples/synthetic_sale_articles_454_491_report.json`. It separates transfer, risk, third-party rights, conformity, acceptance, payment, and remedies without deciding a court outcome.

Generate the reviewed special-supply report for articles 506–524 of the Russian Civil Code:

```bash
python scripts/export_synthetic_supply_evaluation.py
```

The output is written to `examples/synthetic_supply_articles_506_524_report.json`. It separates qualification, acceptance, short delivery, defects, unilateral refusal, and price damages without deciding a court outcome.

Generate the current Phase 0 readiness report:

```bash
python scripts/export_phase0_readiness_report.py
```

The output is written to `examples/phase0_readiness_report.json`.

Generate the synthetic supply benchmark report:

```bash
python scripts/export_synthetic_supply_benchmarks.py
```

The output is written to `examples/synthetic_supply_benchmark_report.json`.

Generate the synthetic supply practice-utility report:

```bash
python scripts/export_synthetic_supply_practice_utility.py
```

The output is written to `examples/synthetic_supply_practice_utility_report.json`.

Generate the synthetic privacy-safe pilot utility schema demo:

```bash
python scripts/export_privacy_safe_pilot_utility.py
```

The output is written to `examples/synthetic_privacy_safe_pilot_utility_report.json`.

Сформировать синтетическую репетицию допуска пилотных данных:

```bash
python scripts/export_synthetic_pilot_rehearsal.py
```

Результат записывается в `examples/synthetic_pilot_rehearsal_report.json`. Артефакт содержит только псевдонимный манифест и хэши содержимого; правила допуска описаны в [спецификации допуска пилотных данных](docs/pilot-data-admission-spec.md).

Generate the synthetic supply red-team report:

```bash
python scripts/export_synthetic_supply_red_team.py
```

The output is written to `examples/synthetic_supply_red_team_report.json`.

Generate the replay-required report for the legacy `contracts-ru-v0@0.1.0` fixture:

```bash
python scripts/export_contracts_package_migration_report.py
```

Команда формирует отчёты о необходимости replay для прежних релизов и пересобирает их относительно `0.50.0`. Отчёты сохраняются как `examples/migrations/contracts-ru-v0-<source>-to-0.50.0-migration-report.json` для `0.1.0`, `0.3.0` и каждого релиза с `0.4.0` по `0.49.0`. Прежние отчёты `*-to-0.17.0` … `*-to-0.49.0` сохраняются как исторические артефакты.


