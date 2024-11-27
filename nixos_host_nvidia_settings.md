this is a guide for doing hyprland on nixos with nvidia

[reddit thread](https://www.reddit.com/r/NixOS/comments/137j18j/need_guide_on_installing_hyprland/)
```nix
services.xserver = {
    enable = true;
    videosDrivers = ["nvidia"];
    displayManager.gdm = {
        enable = true;
        wayland = true;
    };
};

hardware = {
    opengl.enable = true;
    nvidia.modesetting.enable = true;
};

# hyprland
programs.hyprland = {
    enable = true;
    xwayland.enable = true;
    nvidiaPatches = true;
};
```

