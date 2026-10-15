# Architektura

## Cel

Opis docelowej topologii homelaba oraz podziału sieci.

## Topologia

```text
Internet
   |
ISP Router
   |
OPNsense (HP t730)
   |
Managed Switch
   |
   +-- VLAN 10 - Management
   +-- VLAN 20 - User
   +-- VLAN 30 - Server
   +-- VLAN 40 - Security
   +-- VLAN 50 - Other
   |
Proxmox (Lenovo ThinkCentre 920q)
```

## VLAN

| VLAN | Nazwa | Przeznaczenie |
|---:|---|---|
| 10 | Management | Zarządzanie urządzeniami |
| 20 | User | Urządzenia użytkownika |
| 30 | Server | Serwery i usługi |
| 40 | Security | Narzędzia i systemy security |
| 50 | Other | Pozostałe urządzenia |

## Zasady

- OPNsense odpowiada za routing i firewall.
- Switch odpowiada za segmentację warstwy 2.
- Proxmox hostuje systemy laboratoryjne.
- Dostęp między segmentami jest kontrolowany przez firewall.
- Zmiany i testy są dokumentowane w odpowiednich modułach.
