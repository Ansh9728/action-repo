# 🚀 action-repo

This is a dummy GitHub repository used to simulate and trigger webhook events such as:

- `push`
- `pull_request`
- `merge` (via pull request merge)

These webhook events are sent to a Flask webhook listener defined in the [webhook-repo](https://github.com/Ansh9728/webhook-repo.git), which processes and stores them in MongoDB.

---

## 🔧 Webhook Setup Instructions

1. **Go to your GitHub repo settings:**

   `Settings` → `Webhooks` → `Add webhook`

2. **Enter the following details:**

   - **Payload URL:** `http://<your-server-or-ngrok>/webhook`
   - **Content type:** `application/json`
   - **Secret (optional):** Leave blank unless implemented
   - **Events to trigger:**
     - ✅ Push
     - ✅ Pull request
   - Click **Add webhook**

---

## ✅ How to Trigger Events

| Event Type     | How to Trigger                                       |
|----------------|------------------------------------------------------|
| **Push**       | Commit and push any file                             |
| **Pull Request** | Create a new PR from one branch to another         |

---

## 🧪 Example Commands

```bash
# Make a commit (push event)
echo "Test $(date)" >> demo.txt
git add demo.txt
git commit -m "trigger push event"
git push origin main

# Create and push a new branch
git checkout -b feature-branch
echo "New feature $(date)" >> feature.txt
git add feature.txt
git commit -m "add feature"
git push origin feature-branch

# Then open a pull request via GitHub UI (pull_request event)
