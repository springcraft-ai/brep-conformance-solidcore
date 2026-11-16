# brep-conformance-solidcore

The [brep-conformance](https://github.com/springcraft-ai/brep-conformance) adapter for
[solidcore](https://github.com/tangency-labs/solidcore): it puts solidcore behind the suite's
protocol, so that the suite can score it.

## Who maintains this

brep-conformance scores a B-rep kernel through an adapter: a small program that answers the suite's
requests with the kernel's own calls. Springcraft, which maintains the suite, wrote this adapter and
maintains it.

- **It is not solidcore's.** Solidcore's maintainers did not write it or choose the tests it runs.
- **A failure can be the adapter's.** A case solidcore fails in the results may be this adapter
  driving it wrongly. Corrections are welcome: open an issue or a pull request.
- **It adds nothing to the kernel.** The adapter is pass-through, as the suite's
  [contract](https://github.com/springcraft-ai/brep-conformance/blob/main/doc/contract.md#what-an-adapter-may-do)
  asks: one call of the kernel for each function, and anything the kernel has no one call for is
  listed as unsupported. What is scored is solidcore, not this code.
- **Solidcore's maintainers are welcome here.** They know best how to drive solidcore, so their
  review and corrections carry the most weight. Ask in an issue to be added as a reviewer.
- **The suite decides what is scored.** An official run uses only a commit of this adapter that the
  suite's maintainers have reviewed as pass-through, whoever wrote it.

## Licences

The adapter in this repository is under the MIT licence: see [LICENSE](LICENSE).

That licence covers the adapter and nothing else. It does not cover the kernel, and nothing here
relicenses the kernel.

solidcore is a separate work under its own licence. Its crate declares `Apache-2.0`; its repository
is the authority on that, not this page.

Building the adapter downloads solidcore from crates.io and links it in, so a built adapter contains
solidcore and is subject to solidcore's terms as well as this repository's.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Every commit needs a `Signed-off-by` line.
