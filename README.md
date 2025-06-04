# agents-using-LangFlow# FlowBit Workflow Orchestration

A workflow orchestration platform with LangFlow agent integration, manual/webhook/cron triggers, execution history, and real-time logs.

---

## Features

- **LangFlow Agent Integration:**  
  Agents (flows) are auto-discovered from the `/flows` directory.
- **Triggers:**  
  - Manual (from UI)
  - Webhook (`/api/hooks/[workflowId]`)
  - Cron (scheduled, persisted)
- **Execution Table:**  
  View and filter all workflow runs.
- **Execution Details Modal:**  
  - Overview, nodes, logs, and raw data tabs
  - Real-time logs via SSE (`/api/langflow/runs/[id]/stream`)
- **API Endpoints:**  
  - `/api/langflow/flows` — List all flows
  - `/api/trigger` — Trigger a workflow
  - `/api/hooks/[workflowId]` — Webhook trigger
  - `/api/cron` — Add/list cron jobs
  - `/api/langflow/runs` — List runs
  - `/api/langflow/runs/[id]` — Run details
  - `/api/langflow/runs/[id]/stream` — Real-time logs

---

## Getting Started

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Start Docker (for LangFlow and Redis):**
   ```bash
   docker compose up
   ```

3. **Start the app:**
   ```bash
   npm run dev
   ```

4. **Add your agent flows:**  
   Place `.json` files in the `/flows` directory.

---

## Usage

- **Trigger workflows** manually, via webhook, or schedule with cron.
- **View execution history** and click for details.
- **See real-time logs** in the "Message Logs" tab.

---

## Project Structure

- `/flows` — LangFlow agent JSON files
- `/app/api` — All backend API routes
- `/lib/cron.ts` — Cron job scheduling and persistence
- `/components` — React UI components

---

## Notes

- All backend endpoints use mock data unless connected to a real workflow engine.
- Real-time logs are streamed using Server-Sent Events (SSE).

---

