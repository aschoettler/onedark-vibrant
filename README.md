# OneDark Vibrant Theme for VS Code

A high-contrast modification of Atom One Dark

## Features

- High contrast dark theme
- Vibrant syntax highlighting

---

# Usage for Helix / NixOS

This repository provides a [flake](https://nixos.wiki/wiki/Flakes) containing [Home Manager](https://nix-community.github.io/home-manager/) modules for setting up this theme, specifically for the Helix editor.

### Available Modules

1.  `homeModules.helix-themes`: Makes the theme available to Helix (adds it to `~/.config/helix/themes/`) but does not activate it. You must set `programs.helix.settings.theme = "onedark-vibrant"` manually.
2.  `homeModules.onedark-vibrant`: Automatically imports the theme _and_ sets it as the active Helix theme (`programs.helix.settings.theme = "onedark-vibrant"`).

### How to Use

**Add the input to your `flake.nix`:**

```nix
# Your existing flake.nix:
{
  inputs = {
    nixpkgs.url = "github:nixos/nixpkgs/nixos-unstable";
    home-manager.url = "github:nix-community/home-manager";

    # Add this repo as a flake input:
    onedark-vibrant.url = "github:aschoettler/onedark-vibrant";
  };

  outputs = { self, nixpkgs, home-manager, onedark-vibrant, ... }: {
    nixosConfigurations.my-machine = nixpkgs.lib.nixosSystem {
      modules = [
        home-manager.nixosModules.home-manager
        {
          home-manager.users.yourusername = {
            # Insert the following snippet here in your flake, or in your `home.nix` file:
            imports = [
              # Option A: Import just the theme files
              # onedark-vibrant.homeModules.helix-themes

              # Option B: Import theme files AND apply the theme automatically
              onedark-vibrant.homeModules.onedark-vibrant
            ];

            # If you chose Option A, you need to set the theme manually:
            # programs.helix.enable = true;
            # programs.helix.settings.theme = "onedark-vibrant";
          };
        }
      ];
    };
  };
}
```

**Rebuild your system:**

```bash
sudo nixos-rebuild switch --flake .#my-machine

# or, if you're using standalone home-manager:
home-manager switch
```
