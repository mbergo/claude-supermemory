## 2025-05-17 - Insecure File Permissions for API Keys
**Vulnerability:** Configuration files containing API keys were created with default system permissions (typically 0644 or 0664), making them readable by other users on the system.
**Learning:** Node.js `fs.writeFileSync` does not restrict permissions by default. For sensitive data like API keys, explicit permission control is required.
**Prevention:** Always specify `{ mode: 0o600 }` in `fs.writeFileSync` options when saving credentials or sensitive configuration to disk.
