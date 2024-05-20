# CSF2024 paper on formal modeling of security ceremonies

The `code-voting.spthy` theory illustrates a possible implementation of
our code voting example ceremony.

The theory was written to be human readable, but leads to too many
unnecessary case distinctions.  We thus embed the "assign" rule in all
rules that require the type assignment specified by that rule.  The
result of this embeding is the `code-voting-automatic.spthy` file.

The `code-voting-automatic.spthy` file was analyzed with Tamarin
1.8. The functional lemma can be automatically proven.

The code-voting theory tries to use Tamarin's built-in knowledge
inference rules for the Dolev-Yao adversary.  This leads to open
chains in Tamarin's dependency graph generation. The use of the
`--auto-sources` flag produces even more open chains. We have therefore
manually written a typing lemma.

The proofs of the typing lemmas as well as the
integrity and secrecy lemmas are still open.
