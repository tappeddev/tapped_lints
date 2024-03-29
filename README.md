# tapped_lints

## Motivation
We have introduced this module to ensure consistency throughout all projects build @Tapped, this will ensure us
fast and secure development.

## How to install this module
1. Add the following to the `dev_dependencies` in your `pubspec.yaml` file:
```yaml
dev_dependencies:
  flutter_lints: ^1.0.0
  tapped_lints:
    git:
      url: https://github.com/tappeddev/tapped_lints.git
      ref: master
```
2. Then run `flutter pub get` to get the dependencies.
3. If you don't have the file `analysis_options.yaml` in the root of you project - create it.
4. Add the following to `analysis_options.yaml`:
```yaml
include: package:tapped_lints/flutter.yaml
```

⚠️ If you are using Flutter 3.10.X or newer, please use the following include: 

```yaml
include: package:tapped_lints/flutter-3.10.yaml
```

⚠️ We need to include flutter_lints to the dev_dependencies otherwise the linter can't find a reference to the module and
we will get the following error in the `Dart Analysis` tap: `warning: The include file 'package:flutter_lints/flutter.yaml' in '/**/.pub-cache/git/tapped_lints-refnumber/lib/flutter.yaml' can't be found when analyzing '/path/to/module'. (include_file_not_found at [] analysis_options.yaml:1)`

## How to add additional rules to the linter

1. In your `analysis_options.yaml` file you can always add additional `rules/excludes/or any other ` like this:
```yaml
include: package:tapped_lints/flutter.yaml

linter:
  rules:
    overridden_fields: false
    
analyzer:
  exclude:
    - 'lib/generated/**'

```