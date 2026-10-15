# HomeLab

Praktyczny homelab do nauki administracji systemami, sieci, bezpieczeństwa i wirtualizacji.

Celem projektu jest zbudowanie działającego środowiska, a następnie udokumentowanie:
- co zostało zbudowane,
- jak zostało skonfigurowane,
- jak zostało przetestowane,
- jakie wnioski wynikają z pracy.

Dokumentacja jest prowadzona w Markdown i przygotowana z myślą o GitHub.

## Roadmap

| # | Moduł | Status |
|---|---|---|
| 01 | OPNsense | ⬜ |
| 02 | VLAN | ⬜ |
| 03 | Proxmox | ⬜ |
| 04 | WireGuard | ⬜ |
| 05 | Monitoring | ⬜ |
| 06 | Security Testing | ⬜ |

## Architektura

```text
Internet
   |
ISP Router
   |
HP t730 / OPNsense
   |
Managed Switch
   |
   +-- VLAN 10 - Management
   +-- VLAN 20 - User
   +-- VLAN 30 - Server
   +-- VLAN 40 - Security
   +-- VLAN 50 - Other
   |
Lenovo ThinkCentre 920q / Proxmox
```

Szczegóły architektury i sprzętu znajdują się w [`docs/`](docs/).

## Struktura repozytorium

```text
homelab/
├── README.md
├── docs/
│   ├── architecture.md
│   └── hardware.md
├── modules/
│   ├── 01-opnsense/
│   ├── 02-vlan/
│   ├── 03-proxmox/
│   ├── 04-wireguard/
│   ├── 05-monitoring/
│   ├── 06-security-testing/
│   └── 07-sophos-firewall/
├── templates/
│   ├── module.md
│   ├── report.md
│   └── lessons-learned.md
└── .gitignore
```

## Jak dokumentować

Każdy moduł ma trzy poziomy dokumentacji:

1. `README.md` — krótki opis modułu i jego finalnego stanu.
2. `reports/` — konkretne prace, konfiguracje i testy wykonywane podczas realizacji.
3. `lessons-learned.md` — problemy, rozwiązania, najważniejsze wnioski i rzeczy do poprawy po zakończeniu modułu.

Nie dokumentuję każdej drobnej zmiany osobno. Raport powstaje wtedy, gdy wykonuję sensowny etap konfiguracji lub test.

## Status

- ⬜ Planned
- 🟨 In progress
- 🟩 Completed

## Dokumentacja

- [Architektura](docs/architecture.md)
- [Sprzęt](docs/hardware.md)
