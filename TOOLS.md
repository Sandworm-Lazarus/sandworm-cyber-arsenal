# Companion tools

[Home](README.md) · [Skill catalog](CATALOG.md) · [Sources and licenses](SOURCES.md)

These are executable tools and frameworks, counted separately from agent skills. Their README/source overviews were inspected; this repository has not installed or run them. Links point to the recorded revision.

**19 tools and frameworks in 9 groups.** See [start here](docs/start-here.md) for task-oriented selections.

| Group | Tools |
| --- | ---: |
| [Skill review](#skill-review) | 2 |
| [AI evaluation](#ai-evaluation) | 5 |
| [Secrets](#secrets) | 1 |
| [Containers / IaC](#containers-iac) | 2 |
| [Supply chain](#supply-chain) | 4 |
| [CI security](#ci-security) | 1 |
| [Code analysis](#code-analysis) | 2 |
| [MCP development](#mcp-development) | 1 |
| [Privacy & data handling](#privacy-data-handling) | 1 |

<a id="skill-review"></a>

## Skill review

| Tool | ใช้ทำอะไร | ต้องมี / ข้อจำกัด |
| --- | --- | --- |
| [skill-scanner](https://github.com/cisco-ai-defense/skill-scanner/tree/c558c421157c546ec417cf23778ce81a3a8f35fd) | ตรวจ pattern, AST/dataflow และเนื้อหา skill | Skill directory และ scanner dependencies. แยก static, optional LLM/cloud และ runtime evidence |
| [agent-scan](https://github.com/snyk/agent-scan/tree/59def8c624f9d7bef4d49992a4da5e68f83f4e75) | ตรวจความเสี่ยง Agent/MCP configuration และ components | MCP config, scanner และ service access ตามโหมด. บางโหมดเริ่ม server หรือส่ง content ไป API; ตรวจ data flow |

<a id="ai-evaluation"></a>

## AI evaluation

| Tool | ใช้ทำอะไร | ต้องมี / ข้อจำกัด |
| --- | --- | --- |
| [SkillEvaluator](https://github.com/NVIDIA/SkillEvaluator/tree/194f7f975e9dbcf5bc795a7de1147e960ea9a40a) | ตรวจโครงสร้างและประเมินผลมี/ไม่มี skill | Skill package, eval tasks และ model/runtime. Experimental; live evaluation อาจมีค่าใช้จ่าย |
| [PyRIT](https://github.com/microsoft/PyRIT/tree/3b70c3c98f2b07b2f0e435d926de3d44a8bd2ec6) | ประเมิน security/safety ของระบบ generative AI อย่างเป็นระบบ | Python และ model/application target ที่ได้รับอนุญาต. การทดสอบสร้างหลาย model calls; กำหนดงบและเก็บผลทั้งสำเร็จและล้มเหลว |
| [garak](https://github.com/NVIDIA/garak/tree/892779207cbc38f65a738ef9cbdfbc1e83aa0b55) | ใช้ probes สำรวจ failure modes ของ LLM application | Python, model connector และ probe configuration. ผลขึ้นกับ probes และ detector; ไม่ใช้สรุปว่าปลอดภัยครอบคลุมทุกกรณี |
| [promptfoo](https://github.com/promptfoo/promptfoo/tree/b3603fab85bb331da98a8b68ca442e1f4af7e368) | ทำ regression eval และเปรียบเทียบ prompts, Agents และ RAG | Node/CLI, provider access และ test cases. API calls มีต้นทุน; ตรวจ cloud/red-team mode และการส่งข้อมูลก่อนใช้ |
| [inspect_ai](https://github.com/UKGovernmentBEIS/inspect_ai/tree/67873ea965f2d5acd46b2327ea17aecff30026c1) | สร้างและรัน model evaluations ที่มี tasks, solvers และ scorers | Python/uv และ model provider หรือ local backend. แยก scorer quality, task revision และ tool permissions ในรายงาน |

<a id="secrets"></a>

## Secrets

| Tool | ใช้ทำอะไร | ต้องมี / ข้อจำกัด |
| --- | --- | --- |
| [gitleaks](https://github.com/gitleaks/gitleaks/tree/5f6ec56cfa6f8c67648d863582c7ae2f206d5c1c) | ค้น credential patterns ใน repository และ files | CLI และ target files/history. README ระบุ feature-complete และรับ security patches; ผู้ดูแลชี้ไป Betterleaks |

<a id="containers-iac"></a>

## Containers / IaC

| Tool | ใช้ทำอะไร | ต้องมี / ข้อจำกัด |
| --- | --- | --- |
| [trivy](https://github.com/aquasecurity/trivy/tree/0e40f8178a375c68aeca146e4dc4e89ff1009587) | ตรวจ vulnerabilities, misconfiguration, secrets และ SBOM | CLI, image/files และ vulnerability database. ฐานข้อมูลและ coverage เปลี่ยนได้; finding ต้องทวน reachability และ false positives |
| [checkov](https://github.com/bridgecrewio/checkov/tree/c7f1a45fac5712d4cbaef22946109e20a41a1cef) | ตรวจ IaC, container และ dependency configuration ก่อน deploy | Python/CLI และ Terraform/Kubernetes/Docker/config files. ตรวจการเรียก API, external modules และ cloud features ตามโหมด |

<a id="supply-chain"></a>

## Supply chain

| Tool | ใช้ทำอะไร | ต้องมี / ข้อจำกัด |
| --- | --- | --- |
| [syft](https://github.com/anchore/syft/tree/a0c0d3890a9d79421c403e8fcadec50a2e55bf21) | สร้าง SBOM จาก container images และ filesystems | CLI และ image/filesystem. เป็น inventory; ใช้ scanner เช่น Grype เพิ่มเพื่อตรวจ vulnerability |
| [grype](https://github.com/anchore/grype/tree/cd1f23eb50dfb52647090158f453c7359172591f) | ตรวจ known vulnerabilities จาก images, filesystems หรือ SBOM | CLI, artifact/SBOM และ vulnerability database. จับคู่ package/CVE ไม่เท่ากับยืนยัน exploitability |
| [osv-scanner](https://github.com/google/osv-scanner/tree/7de3a036f48e34cdb3a1d396143b11dbba34be52) | จับคู่ dependencies กับข้อมูลช่องโหว่ OSV | CLI, lockfiles/source และ database access ตามโหมด. ต้องระบุ artifact และ database revision เพื่ออธิบายผลที่เปลี่ยนตามเวลา |
| [scorecard](https://github.com/ossf/scorecard/tree/5a951604a5ff7d99b7222139ba522237c58228af) | ตรวจสัญญาณ security hygiene ของ open-source repository | Repository metadata และ API access ตาม checks. Score เป็น hygiene indicators ไม่ใช่การรับรองว่าโค้ดไม่มีช่องโหว่ |

<a id="ci-security"></a>

## CI security

| Tool | ใช้ทำอะไร | ต้องมี / ข้อจำกัด |
| --- | --- | --- |
| [zizmor](https://github.com/zizmorcore/zizmor/tree/33ece2d3d6c60f3d669b8a69e095f60d8a980c0b) | ตรวจ CI/CD config รวม GitHub Actions และ permission risks | Workflow/config files และ CLI. Static analysis; ต้องทวน reusable actions และบริบท runner เพิ่ม |

<a id="code-analysis"></a>

## Code analysis

| Tool | ใช้ทำอะไร | ต้องมี / ข้อจำกัด |
| --- | --- | --- |
| [codeql](https://github.com/github/codeql/tree/ccc03491fc436578bfeecb7e75305d4d64e02118) | ใช้ query libraries และ checks สำหรับ semantic security analysis | CodeQL CLI/database และ toolchain ตามภาษา. MIT ใน repo นี้ครอบคลุม queries/libraries; CLI มีเงื่อนไขแยก |
| [semgrep](https://github.com/semgrep/semgrep/tree/06d9993409f6698f78f6956cd39d968e7f4d7b6a) | ค้น pattern และ taint flows ด้วย static analysis | CLI และ rulesets ตาม engine/edition. Engine, rules และ Pro features ใช้เงื่อนไขต่างกัน; ตรวจ license และ telemetry |

<a id="mcp-development"></a>

## MCP development

| Tool | ใช้ทำอะไร | ต้องมี / ข้อจำกัด |
| --- | --- | --- |
| [MCP Inspector](https://github.com/modelcontextprotocol/inspector/tree/4d3464cb3a6dde609d7b5ac24c440b947eb40f23) | ตรวจและเรียก MCP servers ผ่าน web, CLI หรือ terminal interface | Node runtime ตาม engine ของ revision, MCP server/config และ connection credentials. เครื่องมืออาจเก็บ OAuth/env secrets; ตรวจ keychain หรือ encrypted storage เมื่อใช้ headless/VPS |

<a id="privacy-data-handling"></a>

## Privacy & data handling

| Tool | ใช้ทำอะไร | ต้องมี / ข้อจำกัด |
| --- | --- | --- |
| [Presidio](https://github.com/data-privacy-stack/presidio/tree/1d7005932261a4b676e045d16fa2965dbc4b4ba2) | ค้นและ de-identify ข้อมูล PII ใน text/images ก่อนนำไปใช้ต่อ | Python, NLP/recognizer dependencies และ anonymization policy ตามข้อมูล. ใช้ canonical community repository; ทดสอบข้อมูลภาษาไทยและ false negatives จริง การตรวจอัตโนมัติไม่รับรองว่าพบ PII ครบ |
