# 2026poster (待定title)
This repository provides supplementary materials for the project, including:
- Dataset summary
- Coding scheme
- Overall descriptive statistics
- Cross-tabulation of Contextual Framing Availability (CFA) and Operational Actionability (OA)

These materials document the data sources, coding criteria, and aggregate results used to analyze dual-use ambiguity in cybersecurity prompts.

---

## Dataset Summary
<h3 align="center">
  <strong>Table 1. Dataset information and prompt counts</strong>
</h3>
<table align="center">
<thead>
<tr>
<th align="left">Dataset</th>
<th align="left">Purpose</th>
<th align="center">Reported</th>
<th align="center">Final</th>
<th align="center">Proportion</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left"><strong>CySecBench</strong> (Wahréus et al., 2025)</td>
<td align="left">Cybersecurity jailbreak evaluation.</td>
<td align="center">12,662</td>
<td align="center">12,662</td>
<td align="center">43.1%</td>
</tr>
<tr>
<td align="left"><strong>CyberLLMInstruct</strong> (ElZemity et al., 2025)</td>
<td align="left">Performance–safety trade-off evaluation.</td>
<td align="center">54,928</td>
<td align="center">11,808</td>
<td align="center">40.2%</td>
</tr>
<tr>
<td align="left"><strong>MalwareBench</strong> (Li et al., 2025)</td>
<td align="left">Robustness against malicious code generation.</td>
<td align="center">3,520</td>
<td align="center">3,168</td>
<td align="center">10.8%</td>
</tr>
<tr>
<td align="left"><strong>CyberattackAssistance</strong> (Bhatt et al., 2023)</td>
<td align="left">Compliance with attack requests.</td>
<td align="center">1,000</td>
<td align="center">993</td>
<td align="center">3.4%</td>
</tr>
<tr>
<td align="left"><strong>LLM Attacks</strong> (Zou et al., 2023)</td>
<td align="left">Adversarial safety bypass evaluation.</td>
<td align="center">520</td>
<td align="center">244</td>
<td align="center">0.8%</td>
</tr>
<tr>
<td align="left"><strong>RMCBench</strong> (Chen et al., 2024)</td>
<td align="left">Malicious code generation resistance.</td>
<td align="center">473</td>
<td align="center">472</td>
<td align="center">1.6%</td>
</tr>
<tr>
<td align="left"><strong>Total</strong></td>
<td align="left">—</td>
<td align="center"><strong>73,103</strong></td>
<td align="center"><strong>29,347</strong></td>
<td align="center"><strong>100.0%</strong></td>
</tr>
</tbody>
</table>

## Dataset locations

| Dataset | Path | Reported Count | Prompt field | Introduction |
|--------|------|------|-------------|------|
| CySecBench | `datasets/CySecBench/Dataset/Full dataset/cysecbench.csv` | 12,662 | `Prompt` | Direct malicious prompts without jailbreak wrapping. |
| CyberattackAssistance | `datasets/CyberattackAssistance/mitre_benchmark.json` | 1,000 | `base_prompt` | Contextually wrapped prompts based on MITRE ATT&CK. |
| CyberLLMInstruct | `datasets/CyberLLMInstruct/dataset_creation/final_dataset/final_cybersecurity_dataset_20260531_042849.json` | 11,906 | `instruction` | Template-generated knowledge Q&A. |
| MalwareBench | `datasets/MalwareBench/dataset/attack_prompts.xlsx` | 3,520 | `prompt` | Full jailbreak wrapping with multiple AttackMethods.|
| RMCBench | `datasets/RMCBench/data/csv/prompt.csv` | 473 | `prompt` | Requests of malicious code generation. |
| llm-attacks | `datasets/llm-attacks/data/advbench/harmful_behaviors.csv` | 520 | `goal` | Direct harmful behavior list. |

**Total：30,081 entries**

> **RMCBench Note**：The folder contains two files：`jailbreak-prompt.csv`（78 entries; jailbreak wrapper templates）and `prompt.csv`（473 entries; actual malicious prompts）。The script uses `prompt.csv`。

---
## Coding scheme
<table>
<thead>
<tr>
<th>Dimension</th>
<th>Operational definition</th>
<th colspan="2">Value</th>
<th>Value’s definition</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan="3"><strong>Contextual Framing Availability (CFA)</strong></td>
<td rowspan="3">Does the prompt provide contextual framing, such as user intent, role, task background, or model behavior settings?</td>
<td colspan="2">[0]</td>
<td>Provides no contextual framing.</td>
</tr>
<tr>
<td rowspan="2">[1]</td>
<td>[A]</td>
<td>Provides contextual framing only in the first sentence, with no further elaboration.</td>
</tr>
<tr>
<td>[B]</td>
<td>Provides contextual framing in the first sentence, with further elaboration elsewhere in the prompt.</td>
</tr>
<tr>
<td rowspan="3"><strong>Operational Actionability (OA)</strong></td>
<td rowspan="3">Does the prompt request concrete operational details, such as specific steps, tools, code, or executable attack procedures?</td>
<td colspan="2">[0]</td>
<td>No concrete operational details requested.</td>
</tr>
<tr>
<td rowspan="2">[1]</td>
<td>[A]</td>
<td>Requests knowledge-level operational details in plain text, such as steps, tutorials, methods, strategies, or algorithmic procedures.</td>
</tr>
<tr>
<td>[B]</td>
<td>Requests weaponized operational details, such as executable code, scripts, programs, viruses, malware, or other functional software artifacts.</td>
</tr>
</tbody>
</table>

---

## Overall descriptive statistics

| Dimension | Code | n | % |
|---|---:|---:|---:|
| CFA | 0 | 25,362 | 86.4% |
| CFA | 1A | 1,111 | 3.8% |
| CFA | 1B | 2,874 | 9.8% |
| OA | 0 | 8,759 | 29.8% |
| OA | 1A | 15,121 | 51.5% |
| OA | 1B | 5,467 | 18.6% |

> **Note.** Percentages may not sum exactly to 100% due to rounding.

---

## CFA × OA cross-tabulation
| CFA level | OA = 0 | OA = 1A | OA = 1B | Total |
|---|---:|---:|---:|---:|
| CFA = 0 | 8,757<br>*34.5%* | 14,488<br>*57.1%* | 2,117<br>*8.3%* | 25,362 |
| CFA = 1A | 2<br>*0.2%* | 285<br>*25.7%* | 824<br>*74.2%* | 1,111 |
| CFA = 1B | 0<br>*0.0%* | 348<br>*12.1%* | 2,526<br>*87.9%* | 2,874 |
| **Total** | **8,759** | **15,121** | **5,467** | **29,347** |
> **Note.** Cell percentages indicate the distribution of operational actionability levels within each CFA level. 

