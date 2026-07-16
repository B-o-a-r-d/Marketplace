# Contributing a plugin

Thanks for extending Board! Listing a plugin here makes it installable at runtime by
any Board instance with the marketplace enabled.

## How to submit

1. **Fork** this repository.
2. Add `plugins/<key>.md` where `<key>` is your plugin's `Plugin::key()` value.
3. Fill the front-matter (see the schema below) and a short markdown description.
4. Open a **pull request**. A maintainer reviews and merges it.

## Requirements

Your plugin must:

- be a public GitHub repository with at least one **published Release** (a tag);
- depend on **`board/plugin-sdk`** only (the host provides Laravel + the SDK) and
  declare a matching constraint (e.g. `"board/plugin-sdk": "^0.2"`);
- expose its provider via `extra.laravel.providers` and a PSR-4 `autoload`.

See the [Creating a plugin](https://github.com/B-o-a-r-d/board/wiki/Creating-a-Plugin)
guide.

## Front-matter schema

| Field | Required | Notes |
|-------|----------|-------|
| `key` | ✅ | Unique, matches `Plugin::key()` |
| `name` | ✅ | Display name |
| `repo` | ✅ | `owner/repo` on GitHub |
| `description` | ✅ | One line |
| `author` |  | Your handle |
| `homepage` |  | URL |
| `icon` |  | A [Phosphor](https://phosphoricons.com) icon name (default `puzzle-piece`) |
| `capabilities` |  | Any of `list-source`, `card-enrichment`, `activities`, `mcp-tools` |
| `category` |  | e.g. `connectors` |
| `package` |  | Composer name (`vendor/name`). When set, instances install via `composer require` (Packagist or their configured sources) instead of the GitHub release zipball — publish the package on [Packagist](https://packagist.org) first. Also enables the download counter. |
| `banner` |  | `https://` image URL shown on the marketplace card (fallback: gradient + icon) |
| `screenshots` |  | List of `https://` image URLs shown in the details modal |

## Review criteria

Because installing runs third-party PHP **in-process**, we review for: a sane,
SDK-only dependency, no obviously malicious behavior, a working release, and accurate
metadata. Listing is at the maintainers' discretion and can be revoked.
