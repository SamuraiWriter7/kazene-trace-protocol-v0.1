# Relationship to Structure Fingerprint

Kazene Trace Protocol v0.1 does not generate structural fingerprints by itself.

Instead, it records and references fingerprints that are created by a separate Structure Fingerprint specification or tool.

This separation is intentional.

Structure Fingerprint answers:

> What is the structure?

Trace Protocol answers:

> Where did that structure appear, and what evidence supports its trace?

---

## 1. Role Separation

| Layer | Primary Role |
|---|---|
| Structure Fingerprint | Defines or generates the structural fingerprint of a work |
| Trace Protocol | Records the provenance and evidence context around that fingerprint |

Structure Fingerprint is the **identity layer**.

Trace Protocol is the **evidence layer**.

They are related, but they should not be merged.

---

## 2. Why They Should Remain Separate

If Trace Protocol tried to generate fingerprints directly, the protocol would become too broad.

It would need to define:

- text normalization,
- structural extraction,
- graph representation,
- rhetorical pattern analysis,
- semantic clustering,
- hashing methods,
- similarity thresholds,
- and model-specific inference rules.

That would make Trace Protocol unstable.

Instead, Trace Protocol only references the fingerprint.

This allows Structure Fingerprint methods to evolve independently.

---

## 3. Minimal Connection Field

In a Trace Record, the relationship is expressed through the `fingerprint` object.

Example:

```json
{
  "fingerprint": {
    "fingerprint_id": "sf_kazene_trace_protocol_001",
    "method": "structure-fingerprint-v0.1",
    "hash": "sha256-0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef",
    "canonicalization": "structure-canonical-v0.1",
    "fingerprint_uri": "https://example.com/fingerprints/sf_kazene_trace_protocol_001.json"
  }
}

This is enough for v0.1.

The Trace Record does not need to include the full fingerprint body.

4. Fingerprint as Reference, Not Ownership Claim

A referenced fingerprint does not automatically prove ownership.

It only indicates that a particular structural representation has been associated with a source work or trace record.

For example, a fingerprint may support later review of:

structural similarity,
conceptual lineage,
publication sequence,
derivative relationships,
influence mapping,
or attribution workflows.

However, the fingerprint alone does not decide:

legal ownership,
copyright infringement,
plagiarism,
royalty entitlement,
or final origin judgment.

That judgment belongs to later review layers.

5. Suggested Structure Fingerprint Responsibilities

A separate Structure Fingerprint specification may define:

Responsibility	Description
Canonicalization	How the source work is normalized before analysis
Structural extraction	How conceptual or rhetorical structure is extracted
Fingerprint generation	How the fingerprint object is created
Hashing	How the fingerprint or canonical representation is hashed
Versioning	How fingerprint method versions are identified
Similarity readiness	What metadata helps later comparison systems

Trace Protocol should not own these responsibilities.

It should only store the reference.

6. Suggested Fingerprint Object Fields

A Structure Fingerprint object may contain fields such as:

{
  "fingerprint_id": "sf_kazene_trace_protocol_001",
  "spec_version": "structure-fingerprint-v0.1",
  "canonicalization": {
    "method": "structure-canonical-v0.1",
    "input_type": "text/markdown"
  },
  "structure_hash": "sha256-0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef",
  "features": {
    "concept_sequence": [],
    "rhetorical_pattern": [],
    "relation_graph": [],
    "key_terms": []
  }
}

This is only an example.

The exact Structure Fingerprint format should remain outside Trace Protocol v0.1.

7. Recommended Flow
1. A source work is published.

2. The source work is normalized.

3. A Structure Fingerprint is generated.

4. The fingerprint receives a fingerprint_id and hash.

5. A Trace Record references that fingerprint.

6. The Trace Record records source, evidence, platform context, and risk metadata.

7. Downstream systems may later use both objects for comparison or lineage review.
8. Why This Improves Longevity

The separation improves long-term compatibility.

Structure Fingerprint can evolve from:

structure-fingerprint-v0.1

to:

structure-fingerprint-v0.2
structure-fingerprint-v1.0

without breaking Trace Protocol.

Trace Protocol only needs to know:

which method was used,
which fingerprint was referenced,
what hash identifies it,
and where the full fingerprint record can be found.

This keeps Trace Protocol lightweight and durable.

9. Relationship to Comparison and Lineage

Structure Fingerprint and Trace Protocol together prepare evidence for later comparison.

But they do not perform the comparison themselves.

A later Comparison or Lineage layer may evaluate:

whether two fingerprints are similar,
whether one work may be derived from another,
whether influence is likely,
whether multiple works share a common structural origin,
or whether a trace should be passed to Allocation Readiness.

This is downstream analysis.

Trace Protocol records the evidence.

Structure Fingerprint defines the structure.

Comparison and Lineage interpret the relationship.

10. Non-Goals

Trace Protocol does not:

define the full Structure Fingerprint format,
decide similarity thresholds,
generate embeddings,
extract discourse graphs,
judge originality,
prove authorship,
or enforce rights.

Structure Fingerprint does not:

manage evidence records,
store platform context,
determine royalty allocation,
enforce licenses,
or make final legal judgments.

Each layer remains narrow.

That narrowness is a design strength.

11. Design Summary
Structure Fingerprint = What the structure is.
Trace Protocol = Where the structure appeared.
Lineage / Comparison = How structures may be related.
Allocation Readiness = Whether review can move toward allocation.
Royalty OS = How value may circulate after review.
Final Note

A fingerprint identifies a pattern.

A trace records its path.

Kazene Trace Protocol v0.1 should not try to become the fingerprint engine.

It should remain the record of where the fingerprint appeared, what evidence supports it, and what risks or uncertainties should be carried forward.
