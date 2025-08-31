pkgname=python-pyproject-hooks
pkgver=1.2.0
pkgrel=2
pkgdesc="A low-level library for calling build-backends in pyproject.toml-based project"
arch=('x86_64')
url="https://pypi.org/project/pyproject_hooks/"
license=('MIT')
depends=('python')
makedepends=(
    'python-build'
    'python-flit-core'
    'python-installer'
    'python-wheel'
)
source=(https://github.com/pypa/pyproject-hooks/archive/v${pkgver}/${pkgname#*-}-${pkgver}.tar.gz)
sha256sums=(d993cda99f6c41c2679a0cd5528fc15608cc114df26553deb41db62185c11206)

build() {
    cd ${pkgname#*-}-${pkgver}

    python3 -m build --wheel --no-isolation
}

package() {
    cd ${pkgname#*-}-${pkgver}

    python3 -m installer -d ${pkgdir} dist/*.whl
}
