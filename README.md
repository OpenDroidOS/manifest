# OpenDroidOS source manifest

Selects OpenHarmony sources, maintained platform forks and shared OpenDroidOS
repositories. The `opendroid-7.0` branch uses OpenHarmony `weekly_20261026`.

Install Repo, Git and Git LFS, then run from an empty source directory:

```sh
repo init -u https://github.com/OpenDroidOS/manifest.git -b opendroid-7.0
repo sync -c -j8 --no-clone-bundle --verbose --fail-fast
repo forall -c 'git lfs pull'
```

The default manifest selects the platform forks, common SoC, common vendor
configuration and tree generator. Board, kernel and device vendor repositories
are cloned or created separately by the porter. Local manifests must not
declare the same projects again.

Source synchronization and build-tool setup are separate steps. Prepare the
OpenHarmony prebuilts before building. Reinitialize or synchronize an existing
checkout only while no build or other sync is running.

Derived from the [OpenHarmony manifests](https://github.com/openharmony/manifest).
Upstream history and license notices are retained. See
[upstream documentation](README.upstream.md) for manifest layout and groups.
