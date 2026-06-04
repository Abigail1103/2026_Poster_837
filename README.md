# 2026poster (待定title)
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

### Dataset locations

| Dataset | Path | Reported Count | Prompt type | Introduction |
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
## Code Table
