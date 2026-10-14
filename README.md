# xzip
XZIP: IconBit-based lossless text compression and smart archiving in Python.


License

XZIP's core software is licensed under the GNU General Public License, version 3.0 only (GPL-3.0-only).

You may use, study, modify, and redistribute this software under the terms of that license. When distributing covered modified versions, you must comply with the GPL's applicable source-code availability, licensing, and notice requirements.

Commercial use and sale are permitted subject to the license terms.

Copyright © 2026 Tylorne,Mr. Parkin & Ask-Andy-AI / the applicable copyright holders.

See the "LICENSE" file for the complete terms.

Project direction: XZIP aims to build an open, testable, and community-improvable foundation for IconBit-based lossless compression. Commercial services and separately developed extensions may be offered under separate terms where legally permitted.

CONTRIBUTING.md

Contributing to XZIP

Welcome to XZIP, an experimental IconBit-based lossless compression and smart archiving project maintained under Ask-Andy-AI.

Our goal is to explore whether compact, reversible tokens representing frequent words, syllables, phrases, and recurring patterns can improve text compression when combined with conventional compression techniques.

We welcome developers, testers, documentation writers, algorithm researchers, and contributors interested in open-source data compression.

1. Project Principles

Every contribution should support these principles:

- Lossless integrity: Decompression must reproduce the original input exactly.
- Transparency: Document encoding rules, token dictionaries, format versions, and compatibility requirements.
- Reproducibility: Tests and benchmarks should be repeatable by other developers.
- Interoperability: Avoid unnecessary dependencies and document platform limitations.
- Open collaboration: Explain changes clearly and welcome constructive technical discussion.
- Honest performance claims: Report measured results rather than assuming IconBit encoding always improves compression.

2. Ways to Contribute

You can help by:

- Improving the Python encoder or decoder.
- Developing or testing IconBit token dictionaries.
- Adding multilingual text test cases.
- Finding bugs or data-corruption edge cases.
- Improving compression ratio, speed, or memory efficiency.
- Writing documentation and format specifications.
- Adding benchmarks against established compression methods.
- Reviewing pull requests and suggesting improvements.

Small, focused contributions are encouraged.

3. Before You Start

1. Read "README.md" and the format documentation.
2. Review the "LICENSE" file.
3. Check existing issues and pull requests to avoid duplicating work.
4. For major algorithm or format changes, open an issue or discussion first.
5. Never submit private data, credentials, copyrighted material without permission, or security-sensitive information.

4. Development Workflow

1. Fork the repository.
2. Clone your fork to your computer.
3. Create a descriptive branch, such as "fix/utf8-roundtrip" or "feature/token-dictionary".
4. Make a focused change.
5. Add or update tests.
6. Run the test suite and relevant benchmarks.
7. Commit your changes with a clear message.
8. Open a pull request describing the change, its rationale, test results, and any compatibility implications.

Do not combine unrelated changes in one pull request unless there is a clear technical reason.

5. Testing Requirements

Correctness takes priority over compression speed or file-size reduction.

Every encoder or decoder change should be tested for exact round-trip recovery:

"decode(encode(original_data)) == original_data"

Where applicable, include tests for:

- Empty input.
- Single-byte and very short input.
- Repeated words and repeated byte patterns.
- Random and incompressible data.
- UTF-8 text, emoji, and multilingual content.
- Punctuation, whitespace, and line endings.
- Binary data, if supported by the implementation.
- Unknown tokens and malformed input.
- Truncated or corrupted archives.
- Dictionary version mismatches.
- Large inputs and boundary conditions.

A decoder must not silently return incorrect data when an archive is invalid. Use a documented error or exception.

Tests should be deterministic where practical and must not depend on private files, network services, or a developer's personal machine.

6. Running Tests

XZIP currently uses Python for its prototype. Follow the commands documented in "README.md".

A typical local workflow is:

python -m venv .venv
python -m pip install -e ".[dev]"
python -m pytest

These commands assume the repository defines an installable Python package and a "dev" optional dependency group. If it does not yet, contributors should follow the actual project setup instructions rather than assuming these commands work.

Do not report a test as passing unless you have actually run it. Include any failures and relevant environment details in your pull request.

7. Benchmarking

When proposing a performance improvement, compare the new version against the previous implementation using the same input data and environment.

Where practical, report:

- Original input size.
- Encoded archive size, including required metadata and dictionaries.
- Compression ratio and percentage size reduction or expansion.
- Encoding and decoding time.
- Memory use for larger inputs.
- Python version, operating system, and test conditions.

Use multiple representative datasets. Repeated text, natural-language documents, multilingual text, and incompressible data may produce very different results.

Never sacrifice lossless correctness to obtain a smaller archive.

8. Format and Compatibility Changes

Changes to the archive format, token mapping, headers, checksums, or dictionary rules must be documented.

When introducing a format change:

- Explain why the change is necessary.
- Identify the format version affected.
- Add tests for old and new formats where compatibility is intended.
- Document migration requirements.
- Avoid silently changing how existing archives are decoded.

The decoder should use explicit, documented rules rather than guessing which format was intended.

9. Code Quality and Security

- Prefer readable, maintainable Python.
- Validate archive lengths, token references, and metadata.
- Avoid unsafe deserialization and unnecessary execution of archive contents.
- Treat archives and dictionaries from unknown sources as untrusted input.
- Avoid adding dependencies without explaining their purpose.
- Never commit API keys, passwords, access tokens, or private credentials.

Report suspected security vulnerabilities privately to the repository maintainer instead of publishing exploit details in an issue.

10. Pull Request Checklist

Before submitting, confirm that:

- [ ] The change has a clear purpose.
- [ ] Relevant tests have been added or updated.
- [ ] Round-trip correctness has been verified for applicable changes.
- [ ] The test suite has been run, and results are reported accurately.
- [ ] Documentation has been updated.
- [ ] Format compatibility implications are explained.
- [ ] No secrets or unauthorized third-party material are included.
- [ ] Performance claims are supported by measurements.

Maintainers may request revisions, additional tests, or changes before merging.

11. Licensing and Contributions

XZIP's core software is intended to be distributed under the GNU General Public License, version 3.0 only (GPL-3.0-only).

By submitting a contribution, you confirm that you have the right to submit it and agree that your contribution may be distributed under the project's applicable license terms.

Do not submit code or other material that you do not have permission to contribute.

Unless a separate agreement says otherwise, contributors retain copyright in their own contributions while granting the rights required by the applicable open-source license.

A separate Contributor License Agreement may be introduced if the project later needs additional licensing flexibility. It is not a requirement for ordinary contributions unless the maintainers announce one.

12. Community Standards

Be respectful, constructive, and technically honest.

Critique code and ideas, not people. Explain disagreements with evidence, reproducible examples, or tests. Harassment, discrimination, deliberate sabotage, and knowingly misleading performance claims are not acceptable.

13. Thank You

Every useful bug report, test, document, benchmark, and code review helps make XZIP more reliable.

Our shared objective is simple:

Build an open, testable, trustworthy approach to IconBit-based lossless compression—one verifiable improvement at a time.

— Ask-Andy-AI / XZIP Project