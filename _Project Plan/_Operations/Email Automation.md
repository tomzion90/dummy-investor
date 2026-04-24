# Email Automation — Approved Scripts + Git Push Notifications

## Script-approved emails — MANUAL (decision locked)

When a script is approved in chat, I output the full email ready for copy-paste into Gmail — subject, body, recipient list. You send it manually. Revisit automation after ~4 weeks once the process is validated.

---

## Git push notifications — GitHub Actions + Gmail SMTP (LIVE)

**Workflow file:** `.github/workflows/notify-on-push.yml`

**What it does:** On every push to `main`, sends an email to the recipients defined in the `MAIL_TO` secret:
- `tomezion@gmail.com`
- `Yuvalvul60@gmail.com`

Recipients are stored as a secret (not hardcoded) so changing the list doesn't require a commit — just update the secret in GitHub settings.

Email contains: commit message, commit hash, author, repo URL, plus the "Active priorities" and "Next session" sections from `PROJECT_STATE.md` as a status snapshot.

### Setup — 3 steps, ~5 minutes

#### Step 1 — Generate a Gmail app password

This is the password GitHub uses to send email AS `yutomshazion@gmail.com`. It's not your Gmail login password — it's a 16-character code just for this.

1. Go to https://myaccount.google.com/security
2. Confirm **2-Step Verification** is ON. If not, enable it first (required for app passwords).
3. Go to https://myaccount.google.com/apppasswords
4. "App name" → type `GitHub Actions Dummy Investor`, click **Create**.
5. Google shows a 16-character code like `abcd efgh ijkl mnop`. **Copy it now.** You can't view it again later.

#### Step 2 — Add three secrets to the GitHub repo

1. Open https://github.com/tomzion90/dummy-investor/settings/secrets/actions
2. Click **New repository secret**. Add:
   - **Name:** `MAIL_USERNAME`
   - **Value:** `yutomshazion@gmail.com`
   - Click **Add secret**.
3. Click **New repository secret** again. Add:
   - **Name:** `MAIL_PASSWORD`
   - **Value:** the 16-character code from Step 1 (paste without spaces)
   - Click **Add secret**.
4. Click **New repository secret** one more time. Add:
   - **Name:** `MAIL_TO`
   - **Value:** `tomezion@gmail.com, Yuvalvul60@gmail.com` (comma-separated, add/remove addresses here anytime without touching the workflow file)
   - Click **Add secret**.

#### Step 3 — Push

Push the workflow file. On the next push to `main`, GitHub Actions runs the workflow and the email lands in your inbox within 1–2 minutes.

### Verifying it works

- After your next push, open https://github.com/tomzion90/dummy-investor/actions
- You'll see a workflow run called "Notify on push to main".
- Click into it to see the logs. If the email step fails, it'll say why (usually: wrong password, 2FA not enabled, or secret name typo).

### Changing the recipient list

Edit the `MAIL_TO` secret at https://github.com/tomzion90/dummy-investor/settings/secrets/actions. No commit or push needed — the change takes effect on the next push.

### Common issues

- **Email never arrives:** check spam folder, then check the Actions tab logs.
- **"Invalid login" error:** app password is wrong or 2FA isn't enabled on the sender account.
- **"Recipient refused":** a recipient email is mistyped.
- **Hebrew characters garbled:** the workflow uses UTF-8 so they should render. If not, paste the problem commit message and I'll fix encoding.

### Turning it off temporarily

Rename the file to `notify-on-push.yml.disabled`, commit, push. Rename back to re-enable.
