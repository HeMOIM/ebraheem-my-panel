# My Panel: Grafana Panel Plugin

**Developed by Ebraheem Abokhalil, Fall 2026**
Course: SEN0415 Advanced Web Programming, İstanbul Kültür University
Group members:  Individual project

A Grafana panel plugin built with `@grafana/create-plugin`. It renders a panel that displays the developer's name, as required by the assignment.

## Links
- GitHub repository: https://github.com/HeMOIM/ebraheem-my-panel.git


## Screenshots
![Plugin running in Grafana](screenshots/screenshot-dashboard.png)
![Plugin edit running in Grafana](screenshots/screenshot-dashboard-edit.png)

## What it does
- Registers a panel visualization called **My-Panel** in Grafana.
- Displays "Developed by Ebraheem Abokhalil, Fall 2026" inside the panel.
- Includes the template's sample elements: a circle, a text option and a series counter.

## Requirements
- Windows with WSL2 (Ubuntu 22.04), or Linux/macOS
- Docker Desktop
- Node.js (installed with nvm) and npm
- Git

## How to install and run
```bash
git clone https://github.com/HeMOIM/ebraheem-my-panel.git
cd ebraheem-my-panel
npm install
npm run dev          # terminal 1: builds the plugin and watches for changes
docker compose up    # terminal 2: starts Grafana with the plugin loaded
```
1. Open http://localhost:3000 (login `admin` / `admin` if asked).
2. Go to **Dashboards** and open **Provisioned my-panel dashboard**, or create a new dashboard.
3. For a new dashboard: **Add visualization**, pick **TestData DB**, then choose **My-Panel** as the visualization.
4. Your name appears at the bottom-left of the panel.

To check the production build:
```bash
npm run build
```

## How it was made
1. Installed WSL2 (Ubuntu 22.04), Docker Desktop and Node via nvm.
2. Generated the plugin with `npx @grafana/create-plugin@latest` (type: panel).
3. Edited `src/components/SimplePanel.tsx` to add the developer's name.
4. Added the developer's name to the panel, and kept it visible in the "no data" view too, so the name always shows.
5. Ran the plugin in Grafana through the provided Docker setup and verified it loads.
6. Verified `npm run build` completes successfully.

## Project files
- `src/components/SimplePanel.tsx`: the panel component
- `src/module.ts`: panel registration and options
- `src/plugin.json`: plugin metadata
- `provisioning/`: sample dashboard and data source loaded automatically
- `dashboard/`: exported JSON of my own demo dashboard
- `screenshots/`: screenshots of the plugin in Grafana

## Bonuses I am claiming
- GitHub: public repository
- Documentation: this README
- Dashboard JSON using the plugin (`dashboard/`)
