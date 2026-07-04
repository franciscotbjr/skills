# skills

Coleção de [Agent Skills](https://agentskills.io) — extensões baseadas em prompts utilizáveis por qualquer agente de IA com suporte ao padrão Skill. Cada skill reside em seu próprio diretório com um `SKILL.md` como entrada e é acionada automaticamente pelo agente (com base na `description` da skill) ou diretamente via `/nome-da-skill`.

> Collection of [Agent Skills](https://agentskills.io) — prompt-based extensions usable by any AI agent that supports the Skill standard. Each skill lives in its own directory with a `SKILL.md` entrypoint and is invoked either automatically by the agent (based on the skill's `description`) or directly via `/skill-name`.

## Skills disponíveis / Available skills

| Skill | Idioma / Language | Descrição / Description |
| :---- | :---------------- | :---------------------- |
| [prosa-completa](prosa-completa/) | Português | Skill agregadora que orquestra sober-prose, verbosity-reduction e pt-br-fullness em uma única passada, com ordem canônica e resolução de conflitos. |
| [prosa-sobria](prosa-sobria/) | Português | Suprime vieses retóricos herdados do treinamento por RLHF em respostas expositivas, técnicas, filosóficas ou analíticas. |
| [pt-br-fullness](pt-br-fullness/) | Português | Preserva elementos morfossintáticos e coesivos do pt-BR (artigos, conectivos, regência, clíticos, subjuntivo, crase, pro-drop) que a geração default tende a deixar cair. |
| [sober-prose](sober-prose/) | English | Suppresses RLHF-induced rhetorical patterns in expository writing in favor of precision and epistemic hedges. |
| [verbosity-reduction](verbosity-reduction/) | English | Detects and removes Verbosity Compensation — padding answers with compressible tokens instead of committing to the answer. |
| [methodological-rigor](methodological-rigor/) | English | Critical audit of argumentation, methodology, and epistemic robustness — questions unstated premises, unverified claims, structural biases, and circular reasoning. |
| [readme-writer](readme-writer/) | English | Guides writing, restructuring, and reviewing README files — extracts the project's fundamentals, designs for the scanning reader, and keeps the file synchronized with the repository. |
