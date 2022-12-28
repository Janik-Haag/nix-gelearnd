## Nix gelernt und IaC
![[nix-logo.png]]

<hr>

## Wohami
- I'm Janik
- Networking, Automation and Chaosevents

---
## What is Infrastructure as Code (IaC)?

- Creditcard
- YAML 
- Internet (other people's computer)


---
## Example:
![[server.svg]]

---
## Classic Setup
- Install LInux on a Server
- apt install git nginx ...
- git clone git@mygit.com/some-examle-repo
- ./install.sh

## IAC 
- describe what you want the server to look like
  
- execute some provisioning tools (e.g. ansible-playbook)
or 
- use ci/cd to deploy automaticly 

---

- <span style="color:#9516AE"><b> Advantages </b></span>
- Faster Deployments
- Less Errors
- Exact Documentation
- Changes are pinned down to a Version
- CI/CD integration
- Colaboration is easier

- <span style="color:#9516AE"><b> Disadvantages  </b></span>
- Steep learning curve
- Converting stuff takes time
- If your do it one time it takes your longer

---
## Common IaC frameworks

- Ansible (meh dosn't really keep it promises)
- Docker-Compose (Networking is horrible)
- Terraform (Never used it)
- Cloud-init (Quite basic)
- Nixos (steep learning curve but otherwise quite good)

---
## Nixos
- Is a lInux distro and not a fork
- Aims to be 100% reproducible
- everything is defined in the nix language (services, networking, applications, etc..)

---
## Nix package management
Installing Software
- temporarily with a nix-shell
- in your environment (per user)
- in your config

--- 
## Nix language
- Functional
- Is used to define Configs, Packages and other nix stuff

---
## Example
Setup the system up for Software Defined Radio

```nix
{ config, pkgs, ... }: # Magic line that exposes system configurations, packages and some other stuff

{
  hardware.rtl-sdr.enable = true;
  environment.systemPackages = with pkgs; [
    dump1090
    gnuradio
    gqrx
  ];
}
```

--- 

## Further Resources 

- [package and config search](https://search.nixos.org/)
- [nix-pills](https://nixos.org/guides/nix-pills/)
- [example-configurations](https://nixos.wiki/wiki/Configuration_Collection)
- [nix-wiki](https://nixos.wiki/)

---
## Thanks for listening

https://github.com/Janik-Haag/nix-gelearnd
![[qr_code.png]]
