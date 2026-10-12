# dspace10-lite

Ready-to-run **DSpace 10** for Windows.

Includes:

- Frontend (Angular UI)
- Backend (REST API)
- PostgreSQL
- Solr

Optimized for low-memory PCs and laptops (**~4 GB RAM**).

> Official images: [https://hub.docker.com/u/dspace](https://hub.docker.com/u/dspace)

---

## Requirements

- Windows 10/11 (64-bit)
- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed and running  
  (Docker Hub login is **not** required)
- **8 GB system RAM recommended** (4 GB total is possible but slow)

---

## Quick Start

1. Extract the **dspace10-lite** folder.
2. Make sure **Docker Desktop** is running (whale icon in the system tray).
3. Double-click **`start.bat`**.
4. Wait for DSpace to become ready:
   - **First run only:** about **10–15 minutes** (depends on internet speed).  
     Docker downloads the images once; this does not happen again on normal starts.
   - **Every start after that:** about **05-10 minutes** until DSpace is up and ready to use.
5. Then open:

**http://localhost:4000**

---

## Create Administrator

Double-click **`create-admin.bat`**.

**Login:**

| Field    | Value                 |
|----------|-----------------------|
| URL      | http://localhost:4000 |
| Email    | admin@example.com     |
| Password | admin                 |

---

## Stop

Double-click **`stop.bat`**.

Data is preserved. You can start again later with **`start.bat`**.  
After the first run, allow about **05-10 minutes** each time for DSpace to be fully ready.

---

## Helper Scripts (Windows)

| File | What it does |
|------|----------------|
| `start.bat` | Start DSpace |
| `stop.bat` | Stop DSpace |
| `create-admin.bat` | Create admin user |
| `status.bat` | Show running containers |
| `logs.bat` | View live logs (Ctrl+C to exit) |

---

## Services & Ports

| Service       | Port | URL                          |
|---------------|------|------------------------------|
| Frontend (UI) | 4000 | http://localhost:4000        |
| Backend (API) | 8080 | http://localhost:8080/server |
| PostgreSQL    | 5432 | localhost:5432               |
| Solr          | 8983 | http://localhost:8983        |

---

## Images Used (Official)

| Component | Image                                    |
|-----------|------------------------------------------|
| Backend   | `dspace/dspace:dspace-10_x`              |
| Frontend  | `dspace/dspace-angular:dspace-10_x-dist` |
| Solr      | `dspace/dspace-solr:dspace-10_x`         |
| Database  | `postgres:15`                            |
| CLI       | `dspace/dspace-cli:dspace-10_x`          |

---

## Notes

- For **testing / learning**, not production.
- Official docs suggest 6–8 GB RAM; this lite setup targets older or low-RAM Windows PCs.
- Always start **Docker Desktop** before using any `.bat` file.
- Do not close Docker Desktop while DSpace is running.
- **First run:** 10–15 minutes (image download, one time, depends on internet).  
  **Later runs:** about 05-10 minutes until the site is fully up.

---

## License

This project only ships configuration and Windows scripts.  
DSpace is licensed under the [BSD license](https://github.com/DSpace/DSpace/blob/main/LICENSE).
