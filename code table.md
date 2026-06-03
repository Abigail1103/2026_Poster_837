<table>
  <thead>
    <tr>
      <th>Dimension</th>
      <th>Operational definition</th>
      <th>Value</th>
      <th>Value’s definition</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="3"><strong>Contextual Framing Availability (CFA)</strong></td>
      <td rowspan="3">
        Does the prompt provide contextual framing, such as user intent, role,
        task background, or model behavior settings?
      </td>
      <td>[0]</td>
      <td>Provides no contextual framing.</td>
    </tr>
    <tr>
      <td>[1A]</td>
      <td>
        Provides contextual framing only in the first sentence, with no further
        elaboration.
      </td>
    </tr>
    <tr>
      <td>[1B]</td>
      <td>
        Provides contextual framing in the first sentence, with further
        elaboration elsewhere in the prompt.
      </td>
    </tr>

    <tr>
      <td rowspan="3"><strong>Operational Actionability (OA)</strong></td>
      <td rowspan="3">
        Does the prompt request concrete operational details, such as specific
        steps, tools, code, or executable attack procedures?
      </td>
      <td>[0]</td>
      <td>No concrete operational details requested.</td>
    </tr>
    <tr>
      <td>[1A]</td>
      <td>
        Requests knowledge-level operational details in plain text, such as
        steps, tutorials, methods, strategies, or algorithmic procedures.
      </td>
    </tr>
    <tr>
      <td>[1B]</td>
      <td>
        Requests weaponized operational details, such as executable code,
        scripts, programs, viruses, malware, or other functional software
        artifacts.
      </td>
    </tr>
  </tbody>
</table>
