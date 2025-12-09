# **YouTube → Discord Auto-Posting Automation (n8n)**

This repository contains **two n8n workflows** that automate posting YouTube channel updates directly to a Discord server using a webhook.

Both workflows fetch new videos from a YouTube RSS feed and send them into a Discord channel.

---

## 🚀 **Overview**

### **Workflow 1 — Manual Execution**

* **Trigger:** Manual Trigger (Run using *Execute Workflow*)
* **Steps:**

  1. Fetch latest items from a YouTube RSS feed
  2. Send the video title to Discord via webhook
* ✔ Useful for testing and demonstrating the logic
* **File:** `My workflow.json`

---

### **Workflow 2 — Fully Automatic YouTube → Discord Automation**

* **Trigger:** RSS Feed Trigger (polls every minute)
* **Steps:**

  1. Detect new YouTube uploads
  2. Send title **+** video link to Discord
* ✔ Full hands-free automation
* **File:** `My workflow 2.json`

---

## 🧰 **Tech Stack**

| Component              | Purpose                                |
| ---------------------- | -------------------------------------- |
| **n8n**                | Workflow automation engine             |
| **RSS Feed / Trigger** | Reads YouTube RSS feed for new uploads |
| **Discord Webhook**    | Posts messages to your Discord channel |
| **YouTube RSS URL**    | Fetches the latest video uploads       |

---

## 🔗 **YouTube RSS Feed URL**

Replace the channel ID with any YouTube channel you want:

```
https://www.youtube.com/feeds/videos.xml?channel_id=UCxR_Nm_MafUQD36R1k8Z01w
```

This feed is used in both workflows.

---

## ⚙️ **How to Set Up & Run the Workflow**

### **1️⃣ Install n8n**

You can install n8n via:

#### **Desktop App**

[https://n8n.io/download](https://n8n.io/download)

#### **Or via NPM**

```bash
npm install -g n8n
n8n start
```

The UI will open at:

```
http://localhost:5678
```

---

### **2️⃣ Import the Workflows**

1. Open **n8n**
2. Click **Import**
3. Upload:

   * `My workflow.json` (manual trigger)
   * `My workflow 2.json` (automatic trigger)

---

### **3️⃣ Set Up Discord Webhook**

1. Open your Discord server settings
2. Go to **Integrations → Webhooks**
3. Click **Create Webhook**
4. Copy the webhook URL
5. Paste it into the **Discord node credentials** inside n8n

It appears as:

```
credentials → discordWebhookApi
```

---

### **4️⃣ Update RSS Feed URL (Optional)**

Inside both workflows, locate:

```
feedUrl: https://www.youtube.com/feeds/videos.xml?channel_id=.....
```

Replace with your own YouTube channel ID if needed.

You may also adjust the polling interval (1 min, 15 min, etc.)

---

### **5️⃣ Run the Workflows**

#### **Manual Workflow**

* Click **Execute Workflow**
* It fetches the RSS feed → sends the title to Discord

#### **Automatic Workflow**

* Toggle it **ON**
* It checks every minute for new uploads

---

## 🧪 **Testing Output**

Your Discord channel should receive:

```
<Video Title>
<Video Link>
```


Just tell me!
