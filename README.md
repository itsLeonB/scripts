# scripts

Scripts for my personal workflows.

## gdrive

Complete Google Drive OAuth & Upload Script with authentication management.

**Features:**

- OAuth 2.0 authentication setup
- Secure token management
- File upload to Google Drive
- Interactive credential configuration

**Usage:**

- `gdrive setup` - Set up OAuth credentials
- `gdrive auth` - Authenticate and get tokens
- `gdrive upload <filepath>` - Upload a file

**Configuration:** `~/.gdrive_config` and `~/.gdrive_tokens`

## portfwd

Advanced Kubernetes port-forwarding manager with configuration files, multiple profiles, automatic restarts, and comprehensive error logging.

**Features:**

- Multiple environment profiles (default, staging, production, etc.)
- Kubernetes context and namespace support
- Automatic restart of failed port forwards
- Comprehensive error logging with rotation
- Support for deployments, services, and pods
- YAML and JSON configuration formats

**Usage:**

- `portfwd [profile]` - Start port forwarding with specified profile (default: 'default')
- `portfwd --logs` - View recent error log entries
- `portfwd --help` - Show help

**Configuration:** `~/.scripts-data/portfwd.yaml` or `~/.scripts-data/portfwd.json`
**Error Log:** `~/.scripts-data/portfwd-errors.log`

**Example Configuration:**

```yaml
default:
  context: ""  # Use current context
  namespace: "my-namespace"
  forwards:
    - name: "api"
      type: "deployment"
      local_port: 8080
      remote_port: 80
```

## cpgrep

Cherry-pick commits using grep pattern with chronological ordering and confirmation.

**Features:**

- Search commits by pattern in commit messages
- Support for specific branch searching
- Chronological ordering (earliest to latest)
- Interactive confirmation before cherry-picking
- Conflict resolution guidance

**Usage:**

- `cpgrep <pattern>` - Cherry-pick commits matching pattern from current branch
- `cpgrep <pattern> <branch>` - Cherry-pick commits matching pattern from specific branch

**Examples:**

- `cpgrep TASK-1` - Find and cherry-pick all commits containing "TASK-1"
- `cpgrep TASK-1 origin/main` - Search for "TASK-1" commits in origin/main branch

## vpn

Comprehensive OpenFortiVPN connection management with OTP authentication and interactive configuration.

**Features:**

- Interactive OTP prompting (secure - not stored in command history)
- Configuration file management with guided setup
- Automatic sudo privilege handling
- Process monitoring and cleanup
- Password preservation during configuration updates

**Usage:**

- `vpn connect` or `vpn c` - Connect to VPN (prompts for OTP code)
- `vpn kill` or `vpn k` - Disconnect VPN
- `vpn configure` or `vpn cfg` - Create/edit configuration file interactively
- `vpn help` or `vpn h` - Show help

**Configuration:** `~/.scripts-data/openforti.cfg`
**Template:** `~/.scripts-data/openforti.cfg.example`

**Configuration includes:**

- VPN server host and port
- Username and optional password storage
- Realm and trusted certificate settings
- Advanced connection options
