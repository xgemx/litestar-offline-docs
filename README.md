# litestar-offline-docs

This package enables "offline mode" for FastAPI (in other words lets you avoid loading assets from CDN).

# Installation

```sh
poetry add litestar-offline-docs
```

# Usage

Just construct static file handler and add it to Litestar application during initialization:

```python
import litestar

from litestar_offline_docs import generate_static_files_config

app = litestar.Litestar(
    static_files_config=[generate_static_files_config()],
    ...
)
```

That's it. Now, the assets for API docs are served locally, not from CDN.

## Bundled Swagger UI

The package bundles [Swagger UI 5.32.0](https://github.com/swagger-api/swagger-ui/releases/tag/v5.32.0),
which adds basic OpenAPI 3.2 support, including the `QUERY` HTTP method.
The JavaScript and CSS files are copied without modification from
[the upstream distribution](https://github.com/swagger-api/swagger-ui/tree/1b33a5976d8f5e02d3bc40de1deae3a4a3642e36/dist).
The Apache 2.0 license and upstream notice are included as
`litestar_offline_docs/static/swagger-ui-LICENSE` and `swagger-ui-NOTICE`.

See also: [fastapi-offline-docs](https://github.com/community-of-python/fastapi-offline-docs).
