# DUB Package Description Schema

This project offers a JSON Schema designed for validating DUB package description files (`dub.json`). Its primary goal is to improve the development experience in IDEs and text editors by enabling intelligent autocompletion and real-time validation for your DUB configurations. Please note that this schema is currently a work in progress.

## Usage

To integrate the schema into your project and benefit from its validation features, add the `$schema` property to your `dub.json` file, pointing to the schema's raw URL:

```json
{
    "$schema": "https://github.com/Ragnarokkr/dlang-dub-schema/raw/refs/heads/master/dub.schema.json"
    // ... your DUB package configuration continues here
}
```

Once added, compatible IDEs and text editors will provide immediate feedback and suggestions as you edit your `dub.json` file.

## Compatibility

This schema is based on the official documentation for DUB package manager version **1.40.0**, dated 2025-04-21. While efforts will be made to keep it current, minor discrepancies might arise with future DUB updates.

## Important Note: DUB Package Manager Warning

This schema file is intended exclusively for use within IDEs and text editors that support JSON Schema validation. **It is not meant to be processed by the DUB package manager directly.** Including the `$schema` property in your `dub.json` will cause DUB to emit a warning message:

```console
Warning [...]dub.json(1:2): $schema: Key is not a valid member of this section. [...]
```

You can safely ignore this warning if you wish to retain the `$schema` reference for continuous IDE support. Alternatively, you may remove the `$schema` property from your `dub.json` file once you are confident of its validity, or before publishing your package to avoid the warning during CI/CD processes.
