---
title: Assessment Items
---

# Assessment Items

Use this tool to **inspect assessment check items** inside a Packet Tracer `.pka` / `.pkt` file and see which items are incorrect compared to the expected values — so you know exactly what to fix.

::: tip How it works
Upload a `.pka` / `.pkt` file (it will be decrypted automatically) or a plain `.xml` file that was already decrypted. The tool reads graded nodes from `COMPARISONS` and compares expected values with the current student network configuration in the first `NETWORK` snapshot.
:::

::: warning Experimental Features
Still `Undertesting` but the real values (expected) are `true` from original pka file
Please don't trust the total correct and incorrect items that are showing here (bugs)
You can the `inspect` that total `Assessment Items` on your `cisco`
:::

<ClientOnly>
  <AssessmentItems />
</ClientOnly>

---

## Understanding the results

| Column | Description |
|--------|-------------|
| **Name** | The human-readable label of the check item. |
| **Path** | The node path built from `<ID>` values — useful for locating the item inside the raw XML. |
| **Incorrect (Current)** | The value currently stored in the student network configuration. |
| **Correct (Expected)** | The target value defined in `COMPARISONS` (`nodeValue` attribute). |

### Check types

| `checkType` | Meaning |
|-------------|---------|
| `1` | The item is graded — its value must match the expected value to receive points. |
| `2` | The item is also graded with an alternative check mode. |

Items with `checkType` 0 are informational only and are **not** included in the comparison.

::: details Tips
- **Need Fixing** items are the ones where the student network value differs from `COMPARISONS`. These are the nodes you need to update in the PKA file to make the activity correct.
- **Already Correct** items already have the right value — no action needed.
- After fixing, use the **[PKA / PKT Converter](/tool)** to re-encrypt your edited XML back to a `.pka` file.
:::
