# RevolunixOS Nix package template

Small example repository for packaging shell applications with a Nix flake. It
demonstrates multiple installed executables, build-time path substitution, a
wrapped runtime dependency, an icon, and a generated desktop entry.

The checked-in example installs `exemple` and `exemple-2`; it is intentionally
minimal and should be renamed when creating a real package.

## Try the template

```bash
git clone https://github.com/RevolunixOS/pkg-template.git
cd pkg-template
nix build
nix run
```

## Adapt it

1. Rename the scripts in `src/`.
2. Update `pname`, `version`, display name, and description in `package.nix`.
3. Replace the icon and desktop-entry fields, or remove them for a CLI-only
   tool.
4. Update `substituteInPlace` for internal executable paths.
5. Add every runtime command to `lib.makeBinPath`.
6. Correct the homepage, license metadata, platforms, and main program.
7. Run `nix fmt`, `nix build`, and the installed program.

## Files

```text
flake.nix    x86_64-linux output and Alejandra formatter
default.nix  traditional callPackage entry point
package.nix  derivation and installation logic
src/         example scripts and icon
```

The flake currently pins NixOS 24.05 and exports only `x86_64-linux`.

## License

See [`LICENSE`](LICENSE).
