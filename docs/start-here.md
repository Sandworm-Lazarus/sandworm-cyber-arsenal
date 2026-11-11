# Start here: Cyber Arsenal

[Home](../README.md) · [Tools](../TOOLS.md) · [Sources](../SOURCES.md)

Select a task, inspect the complete pinned package, then try a bounded synthetic fixture. These are reading paths and prototype ideas, not tested integrations.

## Review code

| Project | ใช้ทำอะไร | Evidence to collect |
| --- | --- | --- |
| [codeql](https://github.com/github/codeql/tree/ccc03491fc436578bfeecb7e75305d4d64e02118) | ใช้ query libraries และ checks สำหรับ semantic security analysis | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [semgrep](https://github.com/semgrep/semgrep/tree/06d9993409f6698f78f6956cd39d968e7f4d7b6a) | ค้น pattern และ taint flows ด้วย static analysis | Version, configuration, one task result, failure behavior and data/permission boundaries |

## Review agents and MCP

| Project | ใช้ทำอะไร | Evidence to collect |
| --- | --- | --- |
| [skill-scanner](https://github.com/cisco-ai-defense/skill-scanner/tree/c558c421157c546ec417cf23778ce81a3a8f35fd) | ตรวจ pattern, AST/dataflow และเนื้อหา skill | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [SkillEvaluator](https://github.com/NVIDIA/SkillEvaluator/tree/194f7f975e9dbcf5bc795a7de1147e960ea9a40a) | ตรวจโครงสร้างและประเมินผลมี/ไม่มี skill | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [agent-scan](https://github.com/snyk/agent-scan/tree/59def8c624f9d7bef4d49992a4da5e68f83f4e75) | ตรวจความเสี่ยง Agent/MCP configuration และ components | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [PyRIT](https://github.com/microsoft/PyRIT/tree/3b70c3c98f2b07b2f0e435d926de3d44a8bd2ec6) | ประเมิน security/safety ของระบบ generative AI อย่างเป็นระบบ | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [garak](https://github.com/NVIDIA/garak/tree/892779207cbc38f65a738ef9cbdfbc1e83aa0b55) | ใช้ probes สำรวจ failure modes ของ LLM application | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [promptfoo](https://github.com/promptfoo/promptfoo/tree/b3603fab85bb331da98a8b68ca442e1f4af7e368) | ทำ regression eval และเปรียบเทียบ prompts, Agents และ RAG | Version, configuration, one task result, failure behavior and data/permission boundaries |

## Inspect supply chain

| Project | ใช้ทำอะไร | Evidence to collect |
| --- | --- | --- |
| [gitleaks](https://github.com/gitleaks/gitleaks/tree/5f6ec56cfa6f8c67648d863582c7ae2f206d5c1c) | ค้น credential patterns ใน repository และ files | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [syft](https://github.com/anchore/syft/tree/a0c0d3890a9d79421c403e8fcadec50a2e55bf21) | สร้าง SBOM จาก container images และ filesystems | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [grype](https://github.com/anchore/grype/tree/cd1f23eb50dfb52647090158f453c7359172591f) | ตรวจ known vulnerabilities จาก images, filesystems หรือ SBOM | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [osv-scanner](https://github.com/google/osv-scanner/tree/7de3a036f48e34cdb3a1d396143b11dbba34be52) | จับคู่ dependencies กับข้อมูลช่องโหว่ OSV | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [scorecard](https://github.com/ossf/scorecard/tree/5a951604a5ff7d99b7222139ba522237c58228af) | ตรวจสัญญาณ security hygiene ของ open-source repository | Version, configuration, one task result, failure behavior and data/permission boundaries |

## Review CI and infrastructure

| Project | ใช้ทำอะไร | Evidence to collect |
| --- | --- | --- |
| [trivy](https://github.com/aquasecurity/trivy/tree/0e40f8178a375c68aeca146e4dc4e89ff1009587) | ตรวจ vulnerabilities, misconfiguration, secrets และ SBOM | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [zizmor](https://github.com/zizmorcore/zizmor/tree/33ece2d3d6c60f3d669b8a69e095f60d8a980c0b) | ตรวจ CI/CD config รวม GitHub Actions และ permission risks | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [checkov](https://github.com/bridgecrewio/checkov/tree/c7f1a45fac5712d4cbaef22946109e20a41a1cef) | ตรวจ IaC, container และ dependency configuration ก่อน deploy | Version, configuration, one task result, failure behavior and data/permission boundaries |

## Inspect MCP and privacy

| Project | ใช้ทำอะไร | Evidence to collect |
| --- | --- | --- |
| [MCP Inspector](https://github.com/modelcontextprotocol/inspector/tree/4d3464cb3a6dde609d7b5ac24c440b947eb40f23) | ตรวจและเรียก MCP servers ผ่าน web, CLI หรือ terminal interface | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [Presidio](https://github.com/data-privacy-stack/presidio/tree/1d7005932261a4b676e045d16fa2965dbc4b4ba2) | ค้นและ de-identify ข้อมูล PII ใน text/images ก่อนนำไปใช้ต่อ | Version, configuration, one task result, failure behavior and data/permission boundaries |

## Skill starting points

| Entry | Task | Review |
| --- | --- | --- |
| [differential-review](https://github.com/trailofbits/skills/blob/e4dd0bb5b15535f7c5a0834187dffba6ac37e4ff/plugins/differential-review/skills/differential-review/SKILL.md) | ตรวจความเสี่ยงที่เกิดจาก diff และผลกระทบต่อผู้เรียกใช้ | entry-reviewed |
| [supply-chain-risk-auditor](https://github.com/trailofbits/skills/blob/e4dd0bb5b15535f7c5a0834187dffba6ac37e4ff/plugins/supply-chain-risk-auditor/skills/supply-chain-risk-auditor/SKILL.md) | ตรวจ dependency, advisory, ผู้ดูแลแพ็กเกจ และ install scripts | entry-reviewed |
| [fp-check](https://github.com/trailofbits/skills/blob/e4dd0bb5b15535f7c5a0834187dffba6ac37e4ff/plugins/fp-check/skills/fp-check/SKILL.md) | ตรวจซ้ำว่ารายงานช่องโหว่มีหลักฐานจริงหรือเป็น false positive | entry-reviewed |
| [agentic-actions-auditor](https://github.com/trailofbits/skills/blob/e4dd0bb5b15535f7c5a0834187dffba6ac37e4ff/plugins/agentic-actions-auditor/skills/agentic-actions-auditor/SKILL.md) | ตรวจ GitHub Actions ที่เรียก AI และเส้นทางข้อมูลจาก PR/issue | entry-reviewed |
| [vetting-agent-extensions](https://github.com/trilwu/secskills/blob/ca53957bcd8e3b83b5d4d190bb3ad008a4f15c84/secskills-core/skills/vetting-agent-extensions/SKILL.md) | ตรวจข้อความ config, hooks และสิ่งที่เริ่มทำงานเมื่อใช้ skill/plugin/MCP | entry-reviewed |
| [prompt-injection](https://github.com/UnitOneAI/SecuritySkills/blob/70bc259bb01abb3015ad2ad859ad5253cbf0bcab/skills/ai-security/prompt-injection/SKILL.md) | ประเมินทางเข้า direct/indirect injection และวางชุดทดสอบป้องกัน | entry-reviewed |
| [analyzing-binaries](https://github.com/trilwu/secskills/blob/ca53957bcd8e3b83b5d4d190bb3ad008a4f15c84/secskills-core/skills/analyzing-binaries/SKILL.md) | วิเคราะห์ executable โดยเริ่ม triage ก่อนเลือกจุด decompile | entry-reviewed |
| [reversing-network-protocols](https://github.com/trilwu/secskills/blob/ca53957bcd8e3b83b5d4d190bb3ad008a4f15c84/secskills-core/skills/reversing-network-protocols/SKILL.md) | เทียบ packet capture กับ client เพื่อกู้ framing และ field ของ protocol | entry-reviewed |
| [analyzing-memory-images](https://github.com/trilwu/secskills/blob/ca53957bcd8e3b83b5d4d190bb3ad008a4f15c84/secskills-defense/skills/analyzing-memory-images/SKILL.md) | วิเคราะห์ RAM dump เพื่อเรียงหลักฐาน process, network และ injection | entry-reviewed |

## Original privacy guard

Run the original [local privacy utility](privacy-guard.md) against the [synthetic policy fixtures](../examples/privacy-fixtures.json). Record its documented field policy, input budgets and masking limits. These cases do not establish general PII-detection coverage or Presidio behavior.

