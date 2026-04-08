# KUBERSCAN - KuberScan_FrontEnd

This repository contains:

- `KuberScan_FrontEnd`: Fresh/Preact frontend dashboard.

## Current Features (Updated)

### Frontend (KuberScan_FrontEnd)

- `/dashboard`
  - Alerts widget shows one alert per pod.
  - Status-aware cards (`open`, `quarantined`, `deleted`).
  - Quarantined/deleted visual overlay with diagonal ribbon.
  - `View Pod` button (`/pod/<base64-pod>`).
  - Local hide button `X` (only hides in dashboard view, does not modify DB).

- `/alerts`
  - Grouped by pod (latest alert).

- `/pod/<base64-pod>`
  - Shows pod alerts.
  - Persistent status from backend (`/data/incidents` + `/data/quarantined`).
  - Actions: `Quarantine Pod`, `Delete Pod`, `Dequarantine Pod` (when applicable).

- `/incidents`
  - Shows incidents individually (not grouped).
  - Each incident has:
    - `View Incident`
    - `Go To Pod`
    - `Delete Incident` (soft delete -> status `deleted`).

- `/incident/<base64-pod>`
  - Pod-specific incident detail.
  - Actions: quarantine/delete/dequarantine pod.
  - `Delete Incident` action available.

- `/quarantine`
  - Lists quarantined pods from backend.

- `/deleted`
  - Lists incidents with `status = deleted`.


### KuberScan_FrontEnd

```bash
deno task dev
```

