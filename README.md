# scripts

Scripts for my personal workflows.

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
