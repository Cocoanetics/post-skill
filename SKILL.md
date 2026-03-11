# Post Skill

This skill allows the agent to interact with IMAP email accounts using the `post` CLI.

## Prerequisites
- The `post` CLI must be installed (`brew install cocoanetics/tap/post`)
- The `postd` daemon must be running (`postd start`)

## Commands

### 1. List Servers
Shows available email accounts configured in Post:
```bash
post list-servers
```

### 2. Check Mailbox Status
Get counts of messages, unseen, and recent emails:
```bash
post status --server <server> --mailbox INBOX
```

### 3. List Emails
List the most recent emails in a mailbox:
```bash
post list --server <server> --mailbox INBOX --limit 10
```

### 4. Fetch Email Content
Read the full body of a specific email by UID. Defaults to Markdown.
```bash
post fetch <uid> --server <server> --mailbox INBOX
```

### 5. Search Emails
Search for specific senders, dates, or keywords:
```bash
post search --server <server> --from "someone@example.com" --since 2024-01-01
```

### 6. Move/Trash Emails
Move emails to another mailbox:
```bash
post move <uid> Archive --server <server>
```
Trash an email:
```bash
post trash <uid> --server <server>
```

### 7. Compose Drafts
Create a draft email (auto-detects Markdown for rich formatting):
```bash
post draft --from <your-email> --to <recipient> --subject "Hello" --body "Your markdown message here" --server <server>
```

### 8. Download Attachments
Download attachments to a local directory:
```bash
post attachment <uid> --output /tmp/ --server <server>
```
