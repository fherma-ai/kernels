# FHERMA Kernels

Solutions to the [FHERMA](https://fherma.io/) kernel catalogue — the reference
answers and the challenge winners, one repository per solution.

Every repository has the same shape: the author on the first line of the
README, the license beside it, and the measured project in `solution/`. What
the platform measures is exactly the commit each catalogue entry pins.

## Encrypted kernels

| Kernel | Specification | Solution | Author | Scheme |
| --- | --- | --- | --- | --- |
| [AXPY](https://fherma.io/kernels/axpy) | `secret-vectors@1.0.0` | [encrypted-axpy-ckks](https://github.com/fherma-ai/encrypted-axpy-ckks) | FHERMA team | CKKS |
| [Matrix Multiplication](https://fherma.io/kernels/matrix-multiplication) | `secret-matrices@1.0.0` | [encrypted-matmul-ckks](https://github.com/fherma-ai/encrypted-matmul-ckks) | [Aikata](https://www.iaik.tugraz.at/person/aikata-aikata/) (TU Graz) | CKKS |
| [Max in encrypted array](https://fherma.io/kernels/max-element) | `u16@1.0.0` | [encrypted-max-element-bgv](https://github.com/fherma-ai/encrypted-max-element-bgv) | hita | BGV |
| [Sign of encrypted values](https://fherma.io/kernels/sign) | `f64@1.0.0` | [encrypted-sign-ckks](https://github.com/fherma-ai/encrypted-sign-ckks) | [Aikata](https://www.iaik.tugraz.at/person/aikata-aikata/) (TU Graz) | CKKS |

## How a solution is shaped

```text
README.md      the author, the signature, the idea
LICENSE
solution/      the measured project: solve.cpp + config.jsonc, generated harness
```

Only `solve.cpp` and `config.jsonc` are authored; at measurement the platform
lays its own copy of every generated file over the clone. Scaffold your own
with the [FHERMA toolchain](https://pypi.org/project/fherma/):

```sh
pip install fherma
fherma implementation init <kernel>/<spec>@<version> --lang cpp
```
